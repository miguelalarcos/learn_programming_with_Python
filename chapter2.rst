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

*class* means that we are going to give the definition of something, in this case a right triangle. When we create a **new triangle** (``RightTriangle(3, 4)``), the method *__init__* [#]_ is called and we can say that **its** *side_a* will be the value in *a* (3), and **its** *side_b* the value in *b* (4).

.. [#] also known as the *constructor*.

When we find ``triangle.area()`` we go to the method [#]_ *area* of the **triangle** instance and it returns **its** *side_a* multiplied by **its** *side_b* and divided by 2.

.. [#] *method* is a function inside a *class*.

You might wonder why do we use the word *self* [#]_. When we find *triangle.area()*, the computer identifies *triangle* as an object, and sets it as the current object. Then, inside *area*, *self* means the current object, i.e, the triangle instance.

.. [#] in Java language the used word is *this*, and in Ruby language it's the symbol *@*.

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
