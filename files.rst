Input and ouput
===============

Open and read
^^^^^^^^^^^^^

We use the global function *open*::

    f = open('my_file.txt', 'r') # f is an object that references my_file
    for line in f:               # we can iterate over the file, line by line
        print(line)
    f.close()

the same with context manager. Note we don't need to call *close*::

    with open('my_file.txt', 'r') as f:
        for line in f:
            print(line)

csv
^^^

In this example we see how to read and how to write a csv::

    import csv

    names = {}

    with open('count.csv', 'r') as csvfile:
        reader = csv.reader(csvfile, delimiter=',', quotechar='"')
        for row in reader:
            name, count, date = row
            if name not in names:
                names[name] = count
            else:
                names[name] += count

    with open('count_output.csv', 'w') as csvfile:
        writer = csv.writer(csvfile, delimiter=',', quotechar='"')
        for item in names.items():
            writer.writerow(item)
