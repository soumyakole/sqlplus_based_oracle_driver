This is an extension of sqlplus\_commando to enable Oracle Proc execution
==========================================================================

Original sqlplus\_commando is available in https://pypi.org/project/sqlplus_commando/


Usage
-----

Just clone this repository and then you can use this driver in your code just like so:

.. code:: python

    from sqlplus_commando import SqlplusCommando

    sqlplus = SqlplusCommando(hostname='localhost', database='test',
                              username='test', password='test')
    result = sqlplus.run_query("SELECT 42 AS response, 'This is a test' AS question FROM DUAL;")
    print result

When query returns nothing (after an ``INSERT`` for instance), method
``run_query()`` will return an empty tuple ``()``. If query returns a
result set, this will be a tuple of dictionaries. For instance, previous
sample code could print:

.. code:: python

    ({'RESPONSE': 42, 'QUESTION': 'This is a test'},)

Instead of running a query you may run a script as follows:

.. code:: python

    result = sqlplus.run_script('my_script.sql')

More details are available in https://pypi.org/project/sqlplus_commando/

Oracle Proc execution
---------------------
