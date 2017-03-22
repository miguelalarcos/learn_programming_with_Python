Dates
=====

::

    from datetime import datetime

    d1 = datetime(1978, 3, 15, 0, 0, 0)
    d2 = datetime.now()

    print(d2 - d1)
    > 14245 days, 19:20:04.399178

    from datetime import timedelta

    tdelta = timedelta(hours=8, minutes=5)
    print(3*tdelta)
    > 1 day, 0:15:00
