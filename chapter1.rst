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

Lists
^^^^^

::

    lista = ['red', 'yellow', 'green']

    print(lista[0])
    # red
    print(lista[1])
    # yellow

Functions
^^^^^^^^^

::

    def triangle_area(side_a, side_b):
        return (side_a*side_b)/2

    z = triangle_area(3, 4)
    print(z)
    # 6

Conditions
^^^^^^^^^^

::

    x = 5

    if x == 0:
        print('x is equal to 0')
    else:
        print('x is not equal to 0')

    # x is not equal to 0

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

Can we tell the computer the same thing with less code?::

        names = ['María', 'Miguel', 'Raquel']

        for name in names: 
            print("hello, my name's", name)

