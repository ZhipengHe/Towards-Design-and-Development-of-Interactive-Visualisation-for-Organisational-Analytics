# Technical Description for OrgMiner-Arya

## 1. Technical Review

### [1] MVC Framework ([source](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller))

Model–view–controller (MVC) is a software design pattern commonly used for developing user interfaces that divides the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user.

#### Interactions Betweeen Components

The MVC design pattern also defines interactions between components, as we can see in the following diagram:

![MVC diagram](Pic\mvc_diagram.png)

- The **model** stores data that is retrieved according to commands from the **controller**
- The **view** generates output for the user based on changes in the **model**
- The **controller** acts on both **model** and **view**; it sends commands to the **model** to update its state and to the **view** to change information presented to users

### [2] Flask ([source](https://flask.palletsprojects.com/en/1.1.x/))

Flask is a lightweight web framework for Python. Here will introduce some key methods in Flask.

#### Routing

Flask use the route() decorator to bind a function to a URL. For example,

```python
@app.route('/')
def index():
    return 'Index Page'

@app.route('/hello')
def hello():
    return 'Hello, World'
```

#### HTTP Methods

By default, a route only answers to GET requests. It can use the methods argument of the route() decorator to handle different HTTP methods. For example,

```python
from flask import request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        return do_the_login()
    else:
        return show_the_login_form()
```

#### Rendering Templates

To render a template you can use the render_template() method. All you have to do is provide the name of the template and the variables you want to pass to the template engine as keyword arguments. Here’s a simple example of how to render a template:

```python
from flask import render_template

@app.route('/hello/')
@app.route('/hello/<name>')
def hello(name=None):
    return render_template('hello.html', name=name)
```

## 2. Components analysis for OrgMiner-Arya

### [1] Model Layer
