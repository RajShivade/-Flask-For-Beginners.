# Flask-Fundamentals : 

# Day 0 – Flask Basics & Python Modules.
## Overview

Day 0 covers the basic foundation before starting Flask:

Python function creation

Module importing

Intro to Client–Server architecture

## Files
    
addition_function.py → Contains add function 
    
    addition_function
    
main.py → Imports and executes function 
    
    main

## Theory

 - Flask → Backend web framework

 - Works on Request–Response model

 - Follows Client–Server architecture

## Learning

 - Functions

 - Modules

 - Code reusability

 - Backend basics

# Day 1 – First Flask Application.
## Overview

Built the first basic Flask app with routes and server execution.

## File

 - app.py → Main Flask application

## Key Code
    from flask import Flask
    app = Flask(__name__)
    
    @app.route("/")
    def greet():
        return "Hello User"
    
    @app.route("/add")
    def add():
        return str(5+4)
    
    app.run(debug=True)

## Routes

 - / → Hello User

 - /add → Returns sum (9)

## Concepts Learned

 - Flask import & initialization

 - Routing / Endpoints

 - Running local server

 - Debug mode

# Day 2 – HTTP Methods & Routing.
## Overview

Learned routing with specific HTTP methods (GET & POST).

## File

 - main.py → Flask routes with methods 

        main

## Key Code
    from flask import Flask
    app = Flask(__name__)
    
    @app.route("/", methods=['POST'])
    def home_page():
        return "Welcome to Home Page"
    
    @app.route("/about_us", methods=['GET'])
    def about_page():
        return "This is the About us page"
    
    app.run(debug=True)

## Routes

 - / → POST → Home Page

 - /about_us → GET → About Page

## Concepts Learned

 - HTTP Methods (GET, POST)

 - Method-based routing

 - Endpoint handling

# Day 3 – Templates & Query Parameters.
## Overview

Connected Flask with HTML template and handled user input via URL query parameters.

## Files

 - main.py → Flask backend logic 

        main

 - home.html → Frontend form page 

        home

## Key Concept
    @app.route("/")
    def index():
        return render_template('home.html')
    
    a = request.args.get("A")
    b = request.args.get("B")
    return str(int(a)+int(b))

## Functionality

 - Form takes two numbers

 - Sends data via GET request

 - Flask reads query params

 - Returns sum

## Example:

    /add?A=5&B=3 → 8

## Concepts Learned

 - render_template()

 - HTML form integration

 - Query parameters

 - request.args

# Day 4 – Forms Handling (POST).
## Overview

Created a user form and handled POST data in Flask with result display.

## Files
 - app.py → Backend form handling 

        app

 - homepage.html → Input form UI 

        homepage

 - result.html → Displays submitted data 

        result

## Key Concept
    @app.route('/submit', methods=['POST'])
    def submit_form():
        name = request.form.get('name')
        return render_template('result.html', name=name)

## Form Features

 - Name & Age

 - Password

 - Search field

 - Gender (Radio)

 - Skills (Checkbox)

## Concepts Learned

 - POST method

 - request.form

 - Form data handling

 - Jinja2 templating

 - Dynamic result rendering
