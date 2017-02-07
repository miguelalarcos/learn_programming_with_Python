Object Oriented Programming
---------------------------

An object is sometihng that has attributes and can execute its functions. For example, a person has the attributes *name*, *age* and *hair_color* and can execute its method [#]_ *set_hair_color*.

.. [#] method is how we call a function in the context of an object

This is how we set an attribute on an object::

    peter.hair_color = 'red'

We are saying that *hair_color* **of** *peter* object **is** red.

This how to do the same through a method::

    class Person:
        def __init__(name, age):
            self.name = name
            self.age = age
            self.hair_color = 'black'

        def set_hair_color(new_color):
            self.hair_color = new_color

    peter = Person('Peter', 33)
    peter.change_hair_color('blue')

*class* means that we are going to give the definition of something, in this case a *Person*. Then, *peter* is an object of type *Person* and ``peter.set_hair_color('blue')`` means that peter object takes control and executes its method *set_hair_color*, i.e, ``self.hair_color = new_color``. It's like peter said: "hair color of self is blue".

The expression ``peter = Person('Peter', 33)`` means that we are creating an object and assigning it to the variable *peter*. Then *peter* executes its *__init__* [#]_ method with the parameters *name* and *age*, 'Peter' and 33.

.. [#] also known as the *constructor*.

Another example::

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
