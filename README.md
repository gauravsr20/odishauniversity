## Introduction

A Todo application developed using Django (Python-based framework) and React. It allows to create todo items and save it in a database. 

## Screenshots

![1](https://user-images.githubusercontent.com/80028439/113283224-9fcc0680-9305-11eb-8289-6fa079bc951c.png)

![2](https://user-images.githubusercontent.com/80028439/113283226-a0649d00-9305-11eb-8859-9a57fa3dd3ee.png)

![3](https://user-images.githubusercontent.com/80028439/113283221-9e9ad980-9305-11eb-9a39-aed64419f747.png)

![4](https://user-images.githubusercontent.com/80028439/113283222-9f337000-9305-11eb-9bd3-752c5ab58837.png)

## Pre-requisite
- **Python3** 
    - https://www.python.org/downloads/
- **React (NodeJS and npm)** 
    - https://nodejs.org/en/download/
    - https://www.npmjs.com/
- **IDE** (such as Visual Studio code)
    -  https://code.visualstudio.com/download

The project has been setup in Windows OS. If you are on a different OS, please refer to the official documentation for installation.

## Tech stack
This project is built using Django, Python, Sqlite and React.

## Downloading the project from repository.
Clone the project to your machine ```[git clone https://github.com/REPO_NAME]```

## Installing the dependencies 

In order to run the project, following dependencies are required  

- **django** (can be installed using ```python3 -m pip install django```)
- **django-cors-headers** (can be installed using ```python3 -m pip install django-cors-headers```)
- **djangorestframework** (can be installed using ```python3 -m pip install djangorestframework```)

## Setting up the project

1. You can open the project in any IDE (such as Visual Studio Code). The project has two folders - **frontend** (contains the UI logic, written in React) and **backend** (contains the business logic, written in Python). 

## Compiling and executing the application
1. Since this application is using both React and Django, we will start their respective servers. For starting Django server, run the following command ```[python manage.py runserver]```. The terminal/command prompt should show the following - 

```
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```

You can launch http://127.0.0.1:8000/ on a browser to see the API response. However, to run the UI and add/remove todo items, you need to start React server.

For starting React server, open a new terminal window and follow the below steps - 
1. Navigate into the frontend directory
2. Install the dependencies ```[npm install]```
3. Run the react server ```[npm start]```

The terminal/command should show the following - 

```
Starting the development server...
You can now view frontend in the browser.
Local:            http://localhost:3000/```
On Your Network:  http://192.168.0.104:3000/
```

You will notice that a browser opens up with http://localhost:3000/, and you can see a ToDo application. You can now maintain your todo list.

## Common issues faced and their resolutions (Django)

1. If there are unapplied migrations, you will see the below warning - 
```
You have unapplied migrations; 
your app may not work properly until they are applied.
```

On the terminal/command prompt, run the following commands (one by one) - 
```
- python manage.py makemigrations
- python manage.py migrate
- python manage.py runserver
```

2. If there is an exception in the code, the server might not restart automatically. You need to manually restart it, by the below command.
```python manage.py runserver```

3. 'manage.py' is a file that contains your server configuration. Always make sure you start the server from the level, where manage.py resides. 

## Common issues faced and their resolutions (React)

1. ```Error: Objects are not valid as a React child```
This could happen because we might be trying to display some data, in render method, which is an object. To resolve this, you need to extract the value from the object and assign/display it.

2. ```Error: Parse Error: Adjacent JSX elements must be wrapped in an enclosing tag```
Return statement of render function have separate elements, for example:

```
return ( 
    <Comp1 />
    <Comp2 />
)
```
 
To resolve this, add an enclosing div tag :
```
return (
    <div>
       <Comp1 />
       <Comp2 />
    </div>
)
```
