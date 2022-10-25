# Connecting to MongoDB using Python

[Source](https://www.mongodb.com/languages/python)

MongoDB works simply with Python to create quick connections. 

## Example

```python
from pymongo import MongoClient

def get_db():

    with MongoClient('mongo_url') as client
        db = client['DB_name']
        collection = db['collection_name']

        record = {
            'username': 'user',
            'email': 'email'
        }

        collection.insert_one(record)
```

The above illustrates creating a connection, setting a record object, and then running a single insert operation against the collection before closing the connection.

Mongo creates a lazy connection as nothing happens with the database until a record is inserted. 

#Python