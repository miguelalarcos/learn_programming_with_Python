Object Oriented Programming
---------------------------

Think in the implementation of a function that calculates the area of a rectangle. You can't name it *area* because you have used this name for the right triangle area. You may call it *rectangle_area* and rename the other as *right_triangle_area*. And, what about the area of a circle? At the end you've got lots of functions something like *..._area*. It's a mess, and the solution is Object Oriented Programming.

And object is sometihng that has attributes and can execute its functions. For example, a person has the attributes *name*, *age* and *hair_color*, for example, and can execute its method [#]_ *change_hair_color*.

.. [#] method is how we call a function in the context of an object

This is how we set an attribute on an object::

    peter.hair_color = 'red'

We are saying that *hair_color* **of** *peter* object **is** red.

This how to do the same through a method::

    class Person:
        def __init__(name, age):
            self.name = name
            self.age = age

        def change_hair_color(new_color):
            self.hair_color = new_color

    peter = Person('Peter', 33)
    peter.change_hair_color('blue')

*class* means that we are going to give the definition of something, in this case a *Person*. Then, *peter* is an object of type *Person*. ``peter.change_hair_color('blue')`` means that peter object takes control and executes its method *change_hair_color*, i.e, ``self.hair_color = new_color``. It's like peter said: "hair color of self is blue".

The expression ``peter = Person('Peter', 33)`` means that we are creating an object and assigning it to the variable *peter*. Then *peter* executes its *__init__* method with the parameters *name* and *age*, 'Peter' and 33.

::

    class Person:
        def __init__(name, age):
            self.name = name
            self.age = age

        def i_am_friend_of(other):
            print(self.name, 'said: I am friend of ', other.name)

    peter = Person('Peter', 33)
    mary = Person('Mary', 32)
    peter.i_am_friend_of(mary)
    # Peter said: I am friend of Mary
