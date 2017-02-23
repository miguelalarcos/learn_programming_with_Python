Advanced
========

Decorators
^^^^^^^^^^

A decorator is a function that receives as argument another function and returns another function. See an example::

    def print_arguments(f):
        def helper(x, y):
            print('arguments:', x, y)
            return f(x, y)
        return helper

    @print_arguments
    def add(x, y):
        return x + y

    result = add(8, 9)
    print(result)

    # arguments: 8 9
    # 17

@ notation means that we apply the decorator *print_arguments* to the function *add*. *print_argument* is called with *add* as argument. Inside *print_argument* we define a *helper* function which will be the function returned. Inside *helper* we print the arguments and return the value returned by *add*.

Generators
^^^^^^^^^^

A generator is a function that has state. It does not use the *return* statement as in normal functions, but the *yield* statement::

    def generate_ints(n):
        for i in range(n):
            yield i

    g = generate_ints(3)
    print(next(g))
    print(next(g))
    print(next(g))

    # 0
    # 1
    # 2

The use of *yield value* means that the *value* is returned, and the function stops at this point. Later it is resumed from this point rather than start from the beginning again. Another way of consume the data produced from the generator::

    for x in generate_ints(3):
        print(x)

Contexts
^^^^^^^^

From http://eigenhombre.com/2013/04/20/introduction-to-context-managers::

    import contextlib
    import time

    @contextlib.contextmanager
    def time_print(task_name):
        t = time.time()
        try:
            yield
        finally:
            print task_name, "took", time.time() - t, "seconds."

    with time_print("processes"):
        [doproc() for _ in range(500)]

    # processes took 15.236166954 seconds.

    with time_print("threads"):
        [dothread() for _ in range(500)]

    # threads took 0.11357998848 seconds.
