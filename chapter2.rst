Object Oriented Programming
---------------------------

Think in the implementation of a function that calculates the area of a rectangle. You can't name it *area* because you have used this name for the right triangle area. You may call it *rectangle_area* and rename the other as *right_triangle_area*. And, what about the area of a circle? At the end you've got lots of functions something like *..._area*. It's a mess, and the solution is Object Oriented Programming.

First we need to understand the concept of "an object takes the control of execution"::

    lista = [13, 3, 7]
    lista.sort()
    print(lista)
    # [3, 7, 13]

When we find the instruction ``lista.sort()`` we are saying that the object *lista* takes the control and executes its *sort* function.

This a simple code of OOP::

    class RightTriangle:
        def __init__(self, a, b):
            self.side_a = a
            self.side_b = b

        def area(self):
            return (self.side_a*self.side_b)/2.0

    triangle = RightTriangle(3, 4)
    print(triangle.area()) # 6.0

*class* means that we are going to give the definition of something, in this case a right triangle. A right triangle is defined by the two sides adjacent to the right angle; call them side\ :sub:`a` and side\ :sub:`b`. The area of a right triangle is :math:`\frac{side_a side_b}{2}`

When we create a **new triangle** (``RightTriangle(3, 4)``), it **takes the control** and executes its method [#]_ *__init__* [#]_. ``self.side_a = a`` means that **side_a of itself** will has got the value in *a* (3).

.. [#] *method* is a function inside a *class*.

.. [#] also known as the *constructor*. It initializes the state of the new object.

When we find ``triangle.area()``, the **triangle** instance takes the control and returns its side\ :sub:`a`  multiplied by its side\ :sub:`b` and divided by 2.

Now, the rectangle example, which is quite similar::

    class Rectangle:
        def __init__(self, a, b):
            self.side_a = a
            self.side_b = b

        def area(self):
            return self.side_a*self.side_b

    rect = Rectangle(2, 3)
    print(rect.area()) # 6

Note that we are using the word *area* both in *RightTriangle* and in *Rectangle*. There's no mess.

Exercise: create a class named *Person* whose constructor receives the name of a person, and has got a method called *my_name_is* that returns "Hello, my name is <the name of the person passed in the constructor>".
