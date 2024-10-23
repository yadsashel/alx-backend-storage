# 0x01. NoSQL - MongoDB Project

## Project Overview
This project introduces the concepts of NoSQL databases, specifically MongoDB. You'll learn how to work with MongoDB, use the mongo shell, and implement database queries using Python with the PyMongo library. By the end, you will be able to perform basic CRUD operations and understand the key differences between SQL and NoSQL databases.

## Learning Objectives
By the end of this project, you should be able to explain the following concepts:
- What NoSQL means and how it differs from SQL
- What ACID properties are
- The concept of document storage in NoSQL
- Different types of NoSQL databases
- The benefits of using a NoSQL database
- How to query, insert, update, and delete information from a MongoDB NoSQL database using Python

## Resources
- [NoSQL Databases Explained](https://www.youtube.com)
- [What is NoSQL?](https://www.youtube.com)
- [MongoDB with Python Crash Course](https://www.youtube.com)
- [MongoDB Tutorial](https://www.youtube.com)
- [MongoDB Shell Methods](https://www.mongodb.com/docs/manual/reference/method/)
- [Aggregation Framework](https://www.mongodb.com/docs/manual/aggregation/)

## Requirements
- Ubuntu 18.04 LTS
- MongoDB 4.2
- Python 3.7 and PyMongo 3.10
- All Python scripts must conform to the Pycodestyle standard
- All files must end with a new line
- The first line of Python files must be `#!/usr/bin/env python3`
- Each file should have documentation (use `__doc__` for modules and functions)

## MongoDB Installation Instructions
1. Install MongoDB 4.2:
    ```bash
    $ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | apt-key add -
    $ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list
    $ sudo apt-get update
    $ sudo apt-get install -y mongodb-org
    ```

2. Start the MongoDB service:
    ```bash
    $ sudo service mongod start
    ```

3. Verify installation:
    ```bash
    $ mongo --version
    MongoDB shell version v4.2.8
    ```

4. Install PyMongo:
    ```bash
    $ pip3 install pymongo
    $ python3 -c "import pymongo; print(pymongo.__version__)"
    ```

## Usage
### Running MongoDB
1. Start MongoDB:
    ```bash
    $ sudo service mongod start
    ```

2. List databases using the mongo shell:
    ```bash
    $ mongo --eval 'db.adminCommand({listDatabases: 1})'
    ```

### Python Example for MongoDB Operations
```python
#!/usr/bin/env python3
from pymongo import MongoClient

# Connect to MongoDB
client = MongoClient('mongodb://localhost:27017/')
db = client.my_database

# Insert a document
db.my_collection.insert_one({"name": "Alice", "age": 30})

# Query a document
print(db.my_collection.find_one({"name": "Alice"}))
