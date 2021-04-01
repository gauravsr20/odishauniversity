## Introduction

A Todo application developed using Django (Python-based framework) and React. It allows to create todo items and save it in a database. 

## Pre-requisite
- **Python3**
- **NodeJS**
- **npm**
- **IDE** (such as Visual Studio code)

## Downloading the project from repository.
Clone the project to your machine ```[git clone https://github.com/REPO_NAME]```

## Installing the dependencies 

In order to run the project, following dependencies are required  

- **django** (can be installed using ```python3 -m pip install django```)
- **django-cors-headers** (can be installed using ```python3 -m pip install django-cors-headers```)
- **djangorestframework** (can be installed using ```python3 -m pip install djangorestframework```)

## Setting up the project

1. You can open the project in any IDE (such as Visual Studio Code). The project has two folders - frontend (contains the React code) and backend (contains the Django code). 

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
