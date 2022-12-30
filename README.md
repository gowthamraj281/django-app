# django-app
This is a to-do app build using django framework of python. Here user can create his todo list by adding items, crossed off the completed items, delete the completed items and can delete all the items.

Additional Python Modules Required:

    1.Django

![todo App](https://raw.githubusercontent.com/gowthamraj281/django-app/main/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/gowthamraj281/django-app.git
```
go inside the cloned repo, and install the django which is requried dependencies for this project
```bash
$ cd todo_app
$ pip install django

After installation of django  run this command for initilize the migration files to migrate for run this app
```bash
$ python manage.py makemigrations
```
This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

End of Project.......
