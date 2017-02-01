Object Oriented Programming
---------------------------

Think in the implementation of a function that calculates the area of a rectangle. You can't name it *area* because you have used this name for the right triangle area. You may call it *rectangle_area* and rename the other as *right_triangle_area*. And, what about the area of a circle? At the end you've got lots of functions something like *..._area*. It's a mess, and the solution is Object Oriented Programming.

This a simple code of OOP::

    class RightTriangle:
        def __init__(self, a, b):
            self.side_a = a
            self.side_b = b

        def area(self):
            return (self.side_a*self.side_b)/2.0

    triangle = RightTriangle(3, 4)
    print(triangle.area()) # 6.0

*class* means that we are going to give the abstract definition of something, in this case a right triangle. Forget for the moment that definition and look at this::

    triangle = RightTriangle(3, 4)

We're saying to the computer: "please, allocate some memory space for a new right triangle, and assign it to the name *triangle*". Now *triangle* references a new *instance* [#]_ of the class RightTriangle.

.. image:: triangle_reference.svg

The expression ``RightTriangle(3, 4)`` not only allocates some space but initializes its state with the data supplied. It's done inside the *__init__* [#]_ method [#]_, where *self* is a reference to the new triangle created, and the expression ``self.side_a = a`` stores the data at the variable *a* (the integer 3) into the attribute [#]_ *side_a* of that new triangle.

.. [#] *instance* is a concrete *object* of a class. For example, Peter is a concrete person of the class Person.

.. [#] *__init__* also known as the *constructor*.

.. [#] *method* is the name we use to refer a function inside a *class*.

.. [#] *attribute* is a variable inside a class.

In the expression ``triangle.area()`` we are calling [#]_ the *area* method **on** the *triangle* instance. Let's go the definition of the method *area*::

    def area(self):
        return (self.side_a*self.side_b)/2.0

.. [#] in *OOP* we say that we *send* the message *area* to the object *triangle*.

*self* is passed, and it is a reference to the *triangle* instance because we're coming from ``triangle.area()``.

Now, the rectangle example, which is quite similar::

    class Rectangle:
        def __init__(self, a, b):
            self.side_a = a
            self.side_b = b

        def area(self):
            return self.side_a*self.side_b

    rect = Rectangle(2, 3)
    print(rect.area()) # 6
