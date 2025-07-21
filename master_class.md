# MasterClass: Understanding FASTAPI,Lambda,Map,Reduct,Postman,Third Party Service Integration concepts
## Overview:
This guide introduces the core building blocks  It covers the following concepts in a structured and practical way:

* Fastapi
* what is Lambda
* what is Map
* what is Reduct
* what is Postman
* what is Third party Service Integration

Each section includes conceptual explanations, code examples, and practical usage of these concepts 

# Section 1: What is FastAPI

## Explanation:

 FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.11 based on standard Python type hints.It is designed for building web APIs quickly and efficiently, with automatic data validation, serialization, and documentation generation.pydantic models it supports asynchronous operations,automatically generate Swagger/OpenAPI docs,and is popularity with companies Netflix,icrosoft

## KeyKey Features:
1. Fast – Very high performance, on par with Node.js and Go.
2. Pythonic – Uses Python type hints for better code completion and error checking.
3. Automatic Docs – Generates interactive API documentation using Swagger UI and ReDoc.
4. Validation – Built-in data validation with Pydantic.
5. Asynchronous Support – Supports async and await for non-blocking code.

## Why Both?
* Swagger UI = Best for developers and testing
* ReDoc = Best for clients, product teams, and long-form API docs

## Tools to Use with FastAPI:
1. Uvicorn – ASGI server to run FastAPI
2. Pydantic – Data validation and serialization
3. Docker – Containerize your FastAPI app

## Install:
* pip install FASTAPI
* install python 
* pip install uvicorn

## Run the server with Uvicorn:
* uvicorn main:app --reload
* main: the Python filename (main.py)
* app: the FastAPI instance inside main.py
* --reload: auto-reloads on code changes


## Example:

FastAPI is known for its speed, automatic documentation with Swagger/OpenAPI, and ease of use.
 from fastapi import FastAPI
``` python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}
```
## Knowledge Check:
1. What is FastAPI and why would you use it?
2. How do you install and run a FastAPI app?
3. What are Pydantic models and how are they used in FastAPI?
4. What are the auto-generated docs in FastAPI?
5. How can FastAPI be used with databases?


# Section 2: what is lambda

## Explanation:
A lambda function is a small, anonymous (unnamed) function defined with the lambda keyword in Python. It's often used for short, throwaway functions, especially as arguments to higher-order functions like map(), filter(), or sorted().

## Example:

* Lambda is a serverless computing service by Amazon Web Services that lets you run code without managing servers.
* It returns the result of the expression when called with the given arguments.

### Lambda Function Example
``` python
add = lambda x, y: x + y
print(add(3, 5))  
### With map()
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x ** 2, nums))
print(squared)  
### With filter()
nums = [1, 2, 3, 4, 5, 6]
even = list(filter(lambda x: x % 2 == 0, nums))
print(even)  
### with Sorting()
words = ['banana', 'apple', 'cherry']
words_sorted = sorted(words, key=lambda word: len(word))
print(words_sorted)
```

# Section 3: what is map

## Explanation:
The map() function in Python applies a given function to all items in an iterable (like a list or tuple) and returns a map object (which is an iterator). It’s commonly used for transforming data.

## Example:
* function: A function to apply to each element
* iterable: A sequence List, tuple
``` python
numbers = [1, 2, 3, 4]
squared = map(lambda x: x ** 2, numbers)
print(list(squared))  
```
## Use cases:

| Use Case               | Example                       |
| ---------------------- | ----------------------------- |
| Apply math operation   | `map(lambda x: x+1, [1,2,3])` |
| Convert data types     | `map(int, ["1", "2", "3"])`   |
| Apply string methods   | `map(str.upper, ["a", "b"])`  |
| Process multiple lists | `map(lambda x,y: x+y, a, b)`  |

## Knowledge Check:
1. What is the map() function in Python?
2. What is the syntax of map()?
3. What type of object does map() return?
4. What are the alternatives to map() in Python?
5. How do you use map() with multiple iterables?

# Section 4: what is Reduct
## Explanation:
reduce() is a function from the functools module that reduces a sequence of elements into a single value by applying a function cumulatively.
## Example:
* function: A function that takes two arguments
* iterable: A sequence
```python
from functools import reduce

numbers = [1, 2, 3, 4, 5]

result = reduce(lambda x, y: x + y, numbers)
print(result)
```
# Section 5: what is Postman

## Explanation:
Postman is a popular tool used to test APIs by sending HTTP requests (like GET, POST, PUT, DELETE) to a server and viewing the responses. It’s commonly used by developers and testers working with RESTful APIs

## Example:
* end-to-end Postman example using a simple FastAPI app.
```python
from fastapi import FastAPI
from pydantic import BaseModel
app = FastAPI()
class Item(BaseModel):
    name: str
    price: float
    in_stock: bool

@app.post("/items/")
def create_item(item: Item):
    return {"message": "Item received", "item": item}
```
### Test with Postman:
* Open Postman
* Select POST method
* Enter the URL:http://127.0.0.1:8000/items/
* Go to the Body tab
* Choose raw and set type to 

### Json:
{
  "name": "Laptop",
  "price": 1299.99,
  "in_stock": true
}

### You Can Also Test:
```python
* GET / → try a basic endpoint
@app.get("/")
def read_root():
    return {"msg": "Hello from FastAPI"}
```
# Section 6: what is Third party Service Integration

## Explanation:
Third-party service integration means connecting your application (web, mobile, backend, etc.) with external services or APIs to extend its functionality — without building everything from scratch.

## Example:
* Authentication (e.g., Google Login)
* Cloud storage (e.g., AWS S3)

### Summary Table
| Category      | Services
| Auth/Login    | Google
| Payments      | Stripe, PayPal, Razorpay
| Maps          | Google Maps, Mapbox 

### Integration Steps:
* Create an account on the third-party service
* Get API keys (usually from a dashboard)

# Section 7:Knowledge Check — Interview Questions
1. What is a third-party service?
2. What tools help test third-party integrations?
3. Why do we use third-party services instead of building in-house?
4. Name some common third-party services used in web development.
5. How do you integrate a REST API from a third-party service in Python?
6. How do you store third-party API credentials securely?

















 































