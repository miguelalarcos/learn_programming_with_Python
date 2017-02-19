Object Oriented Programming
---------------------------

Class and object
^^^^^^^^^^^^^^^^

Think in a table. You can think in an abstact way and say that a table has got a board and some legs. And it is made of some material. This is the *class* Table. Now think in a concrete table, the table in my kitchen, made of wood and with 4 legs. This is an instance table from the class Table, and it's an object.

Let's introduce the definition of the class *Table*::

    class Table:
        def __init__(self, material, legs, color):
            self.material = material
            self.legs = legs
            self.color = color

        def info(self):
            print("I am a table made of", self.material, "and with", self.legs,"legs.")

And forget it for a moment. Let's see how we create a table::

    kitchen_table = Table('wood', 4, 'white')
    kitchen_table.info()

    # I am a table made of wood and with 4 legs.

How do we change and attribute of the table? This way::

    kitchen_table.color = 'red'

Now is the moment to examine the code of the class. When we create a table with ``kitchen_table = Table('wood', 4, 'white')``, this new table will execute the *__init__* [#]_ method [#]_::

    def __init__(self, material, legs, color):
        self.material = material
        self.legs = legs
        self.color = color

.. [#] also known as the *constructor*.
.. [#] method is how we call a function in the context of an object

Note that *wood* value goes to *material* parameter, *4* to *legs* and *white* to *color*. Then, what is ``self.color = color``? *self* is the newly created table, so it is assigning the value *white* to its attribute *color*.

Imagine the same through a method::

    class Table:
        ...
        def change_color(self, color):
            self.color = color

    table = Table('wood', 4, 'white')
    table.change_color('yellow')

``table.change_color('yellow')`` means that *table* is going to execute its method *change_color*, which has ``self.color = color``. In this case *self* is the object *table*.

Inheritance
^^^^^^^^^^^

A class can extends the definition of another class, called the *base* class. Imagine a *Pet* class as a base class::

    class Pet:
        def __init__(self, name):
            self.name = name

        def speak(self):
            print(self.name, ':')

        def my_name_is(self):
            print('my name is', self.name)

And now the class *Cat* that extend class *Pet*::

    class Cat(Pet):
        def __init__(self, name, color):
            super().__init__(name)
            self.color = color

        def speak(self):
            super().speak()
            print('miauuuuu')

``class Cat(Pet):`` means that the class *Cat* will have the methods of *Pet*. We can do the next thing::

    mifu = Cat('Mifu')
    mifu.my_name_is()

    # my name is Mifu

As you can see, *my_name_is* is not defined in *Cat*, but in *Pet*.

*Cat* would have the method *__init__* from *Pet*, but it's overwritten. But we have a problem, because the *name* attribute is initialized in the *__init__* method of *Pet*. How do we access this?::

    super().__init__(name)

``super()`` means that this instance of Cat is going to be treated as a instance of *Pet*. So we call *__init__* of *Pet* for this cat.

As we can see, *speak* method is also overwritten::

    mifu = Cat('Mifu')
    mifu.speak()

    # Mifu :
    # miauuuuu
