# Python's Null is None



```python

# We'd like to connect to a database. We don't know if the authentication
# details are correct, so we'll try. If the database connection fails,
# it will throw an exception. Note that MyDatabase and DatabaseException
# are not real classes, we're just using them as examples.
 
database_connection = None
 
# Try to connect
try:
    database = MyDatabase(db_host, db_user, db_password, db_database)
    database_connection = database.connect()
except DatabaseException:
    pass
 
if database_connection is None:
    print('The database could not connect')
else:
    print('The database could connect')
    ```
    