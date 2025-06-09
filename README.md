README

Overview
This project contains two FastAPI applications:

1. Task Management API (fastapi-curd.py)
Implements basic CRUD operations to manage tasks.

Each task includes the following attributes:

id: Unique UUID identifier

title: Task title

description: Optional task description

completed: Boolean flag indicating if the task is completed

2. User Authentication API (fastapi-tutorial.py)
Implements user registration, login, and token-based authentication using JWT (JSON Web Tokens).

Secures endpoints and stores user data in a simulated database.

Requirements and Installation
Make sure you have a recent version of Python installed.

Install the required packages using pip:

css
Copy
Edit
pip install fastapi uvicorn python-jose passlib[bcrypt] python-multipart
Running the Applications
Task Management API
Run the following command:

nginx
Copy
Edit
python fastapi-curd.py
The API will be available at:
http://localhost:8000/tasks/

User Authentication API
Run the following command:

nginx
Copy
Edit
python fastapi-tutorial.py
Login endpoint:
http://localhost:8000/token

Current user info endpoint:
http://localhost:8000/users/me/

API Endpoints
Task Management API Endpoints
Operation	HTTP Method	Path	Description
Create a new task	POST	/tasks/	Create a new task
Retrieve all tasks	GET	/tasks/	Get a list of all tasks
Retrieve task by ID	GET	/tasks/{task_id}	Get a specific task by its ID
Update task by ID	PUT	/tasks/{task_id}	Update details of a specific task
Delete task by ID	DELETE	/tasks/{task_id}	Delete a specific task by its ID

User Authentication API Endpoints
Operation	HTTP Method	Path	Description
Generate access token	POST	/token	User login and generate JWT token
Get current user info	GET	/users/me/	Retrieve info about the logged-in user
Get current user's items	GET	/users/me/items	Retrieve items owned by the current user

Notes
The authentication API uses the python-jose library for encoding and decoding JWT tokens.

The python-multipart package is required to handle form data in login requests.

You can test and explore the API interactively via FastAPI’s automatic docs at:
http://localhost:8000/docs
