Modules
=======

Your normally don't write all the code in only one file. The best approach is to aggrupe functionality related to something specific in one file.

Imagine a file called *mathlib.py* that contains the next code::

    # mathlib.py

    def add(a, b):
        return a + b

    def subtract(a, b):
        return a - b

And then, in your main file::

    # main.py
    import mathlib

    print(mathlib.add(3, 5))
    > 8

or::

    # main.py
    from mathlib import add

    print(add(3, 5))
    
