Learn by example, not by heart
==============================

In the 80's I learned to program with my Amstrad CPC-464. No one showed me how to do it, I just learned the BASIC language by modifying examples, normally simple games. Today, the most suitable language to learn programming may be Python. Let's dive into coding.

The basics of coding
--------------------

Printing
^^^^^^^^

How to tell the computer to print some text::

    print("hello, I am a computer!")
    # hello, I am a computer!

or we can print a number::

    print(7)
    # 7

Variables
^^^^^^^^^

::

    x = 1
    y = 2
    z = x + y
    print(z)
    # 3
    z = 8
    print(z)
    # 8

Lists
^^^^^

::

    lista = ['red', 'yellow', 'green']

    print(lista[0])
    # red
    print(lista[1])
    # yellow

We access the first position of a list with the index *0*. And this is how we modify a list::

    lista[0] = 'black'
    print(lista)
    # ['black', 'yellow', 'green']

Conditions
^^^^^^^^^^

Please note the *==* for the condition and the *=* for the asignment::

    x = 5

    if x == 0:
        print('x is equal to 0')
    else:
        print('x is not equal to 0')

    # x is not equal to 0


Functions
^^^^^^^^^

Suppose we want to calculate the area of a right triangle::

    def area(side_a, side_b):
        return (side_a*side_b)/2.0

    z = area(3, 4)
    print(z)
    # 6.0

*def* means we are going to write the definition of a function. A function may have some variables as input, and an output, a calculated value. The calculated value is returned by the keyword *return*. Here is a more sofisticated function, with several apparition of the word *return*::

    def comparison(a, b):
        if a == b:
            return 0
        elif a < b:
            return 1
        else:
            return -1

Now a function that returns a text like "2 days, 7 hours, 5 minutes and 30 seconds" given a number of seconds::

    def time_repr(seconds):
        seconds_in_a_day = 24*60*60
        seconds_in_an_hour = 60*60
        seconds_in_a_minute = 60

        days = seconds // seconds_in_a_day
        rest = seconds % seconds_in_a_day

        hours = rest // seconds_in_an_hour
        rest = rest % seconds_in_an_hour

        minutes = rest // seconds_in_a_minute
        seconds = rest % seconds_in_a_minute

        return "%d days, %d hours, %d minutes and %d seconds" % (days, hours, minutes, seconds)

    t = time_repr(1000000)
    print(t)

    # 11 days, 13 hours, 46 minutes and 40 seconds

Functions with named parameters
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Suppose the next function::

    def f(a, b):
        return a + b*2

We can call the function as we have seen::

    z = f(1,2)
    print(z)

    # 5

But we can also use named parameters. The next calls are the same::

    f(a=1, b=2)
    f(b=2, a=1) # note we alter the order of the parameters

Loops
^^^^^

Let's examine this example::

    print("hello, my name's María")
    print("hello, my name's Miguel")
    print("hello, my name's Raquel")

    # hello, my name's María
    # hello, my name's Miguel
    # hello, my name's Raquel

You can see repetitive code::

    print("hello, my name's ...")

Can we tell the computer the same thing with less code? Yes, iterating over a list::

    names = ['María', 'Miguel', 'Raquel']

    for name in names:
        print("hello, my name's", name)

This mean that for each *name* inside the list *names*, print a text. You can choose whatever word instead of *name*, but remember to use words for the variables according to the circumstances.

Loop over a list of integers::

    for i in [0, 1, 2, 3]:
        print(i)

But if we want to iterate over a list of 1000 integers, should I write the entire list? No, we use the *range* function::

    for i in range(1000):
        print(i)

    # 0
    # 1
    # 2
    ...
    # 998
    # 999

Dictionaries
^^^^^^^^^^^^
Dictionaries are similar to lists, but instead of having an integer as index, it can have other kind of objects, like strings::

    dct_DNI = {'4842R': 'Miguel', '2256Z': 'Raquel'}

    person = dct_DNI['4842R']
    print(person)

    # Miguel

We can add elements to dictionaries::

    dct_DNI['2234H'] = 'Paul'

Methods of strings and lists
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We can manipulate strings and lists with the dot notation::

    t = 'hello'
    v = t.capitalize()
    print(v)

    # Hello

We say that *capitalize* is a method of the objects type *string*. We'll see more on this in the Object Oriented Programming chapter. Another example, sorting a list::

    lista = [3, 1, 7, 2]
    lista.sort()
    print(lista)

    # [1, 2, 3, 7]

Have you noticed that *capitalize* returns a new string while sort does not return a new list? This is because strings are immutable while lists are mutable objects.

You can see more string-methods_.

.. _string-methods: https://docs.python.org/3/library/stdtypes.html#string-methods
