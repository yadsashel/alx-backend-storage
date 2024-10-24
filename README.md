# 0x02. Redis Basic - Project README

## Description

This project introduces the basics of **Redis** and demonstrates its use in Python applications. Redis is a powerful in-memory data structure store used as a database, cache, and message broker. This project aims to teach how to use Redis for basic operations, implement simple caching techniques, and explore Redis commands and their Python equivalents.

## Learning Objectives

- Use Redis for basic operations such as storing and retrieving data.
- Implement Redis as a simple cache.
- Understand how to store and retrieve various data types using Redis.
- Learn about Redis commands and their usage in Python.

## Requirements

- All Python scripts are written in Python 3.7.
- All code must follow **pycodestyle** style guidelines (version 2.5).
- Modules, classes, and functions must include proper documentation.
- All functions and coroutines must be type-annotated.
- Redis should be installed on Ubuntu 18.04.

## Installation

### Install Redis on Ubuntu 18.04

```bash
sudo apt-get update
sudo apt-get install redis-server
```

### Install Redis Python Client

```bash
pip3 install redis
```

### Configure Redis

To ensure Redis listens on `localhost`, update the `bind` configuration:

```bash
sudo sed -i "s/bind .*/bind 127.0.0.1/g" /etc/redis/redis.conf
```

## Project Structure

- **`exercise.py`**: Contains the core Python code for Redis operations, including storing, retrieving, and counting Redis interactions.
- **`main.py`**: Example script showcasing how to use the `Cache` class and its methods.

## Tasks

### 0. Writing Strings to Redis
- Implement the `Cache` class to handle storing data in Redis.
- Create a `store` method to generate a unique key and store data.

### 1. Reading from Redis and Recovering Original Type
- Implement a `get` method that retrieves data from Redis and converts it to the correct type using a callable.
- Implement helper methods `get_str` and `get_int`.

### 2. Incrementing Values
- Create a `count_calls` decorator to count how many times `Cache` methods are called using Redis `INCR` command.

### 3. Storing Lists
- Implement a `call_history` decorator to store input and output history of methods in Redis lists.

### 4. Retrieving Lists
- Implement a `replay` function that displays the history of inputs and outputs for a specific function using Redis lists.

## Usage

### Example Code for Storing Data

```python
#!/usr/bin/env python3
from exercise import Cache

cache = Cache()
data = "Hello, Redis!"
key = cache.store(data)

print(f"Stored data under key: {key}")
retrieved = cache.get(key)
print(f"Retrieved data: {retrieved}")
```

## Testing

You can run the examples provided in `main.py` to test the different functionalities implemented in the project. 

## Resources

- [Redis Crash Course Tutorial](https://www.youtube.com/watch?v=Hbt56gFj998)
- [Redis Commands](https://redis.io/commands)
- [Redis Python Client](https://pypi.org/project/redis/)
- [How to Use Redis with Python](https://realpython.com/python-redis/)

## Author

This project was developed as part of the ALX Backend Specialization course.
