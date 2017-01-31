Object Oriented Programming
---------------------------

Think in the implementation of the area of a rectangle. You can't name it *area* because it is used for the right triangle area. You may call it *rectangle_area* and rename the other as *right_triangle_area*. And, what about the area of a circle? At the end you've got lots of functions something like *..._area*. It's a mess, and the solution is the Object Oriented Programming.


This a simple code of OOP::

    class RightTriangle:
        def __init__(self, side_a, side_b):
            self.side_a = side_a
            self.side_b = side_b

        def area(self):
            return (self.side_a*self.side_b)/2.0

    triangle = RightTriangle(3, 4)
    tr_2 = RightTriangle(50, 21)

    print(triangle.area()) # 6.0
    print(tr_2.area()) # 525.0

*class* means that we are going to give the abstract definition of something, in this case a right triangle. It's given in the ``__init__`` method (*method* is the name we use to refer a function inside a *class*). The computer allocates a space of memory for every triangle you create with the expression ``variable = RightTriangle(side_a, side_b)``. We move to *__init__* and in a first step we can think that the word *self* refers to this space of memory, where we save the data of the sides adjacent to the right angle.

*triangle* and *tr_2* are called *instances* of the class *RightTriangle*. And now there's no ``area(triangle)`` but the reverse ``triangle.area()``. We move to *area* method and the computer passes the memory space  of *triangle* in *self*. When we are at ``tr_2.area()``, the computer passes us the space of *tr_2* in *self*.

Now, the rectangle example::

    class Rectangle:
        def __init__(self, side_a, side_b):
            self.side_a = side_a
            self.side_b = side_b

        def area(self):
            return self.side_a*self.side_b

    rect_1 = Rectangle(2, 3)
    print(rect_1.area()) # 6

We've defined another *area* method, inside the class *Rectangle*, and we use it like that: ``rect_1.area()``. Please note that in both cases, the triangle and rectangle, we use the same word *area*.

self
^^^^

What is *self* exactly? When the computer allocates some memory space for an instance of a class, the space is not only for the data of the instance. There's also some space to indicate the *class* of the instance and other things. So, *self* is a reference to that whole space. Thanks to the reference *self* you can access not only to the data but the methods defined in the class. E.g::

    class Cat:
        def __init__(self, name):
            self.name = name

        def speak(self):
            print(self.name, ':', 'miauuuu!')

        def at_night(self):
            self.speak()
            self.speak()

    garfield = Cat('Garfield')
    garfield.at_night()
    # Garfield : miauuuu!
    # Garfield : miauuuu!

We create a cat called *Garfield*. The computer allocates some space for it and returns it to the variable *garfield*. We call the method *at_night* on the instance *garfield*. It's an instance of the class *Cat*, and here there's a method *at_night*, so We go to the this definition. The reference to *garfield* is passed as the argument *self*. Then *speak* is called on *self* (the instance *garfield*). We go to the definition of *speak* and print some text. Note we access the attribute *name* of *self*, i.e. *garfield* instance.
