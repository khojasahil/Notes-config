# Notes-config

Install VS code
	Install Python3(market place)
	Create project folder
	Launch terminal (ctrl + ' or è)
	Install venv (sudo apt-get install python3-venv)
	Create venv 11_env (python3 -m venv 11_env)
	Activate (source ll_env/bin/activate)
	Install Django (pip3 intall django)
	
Create project in venv activated
	django-admin.py startproject learning_log .
		Creates a folder Learning_log
		Creates files : 
			Settings.py : controls how django interacts your the system and manages the project, ex : we have to add the app name
			Urls.py : Tells django which pages to build in response to browser request
			Wsgi.py : Helps Django serve the files it creates (Web server gateway interface)

Create Database
	python manage.py migrate
		Creates new database for us (Sql lite)

Create new app (learning_logs)
	python manage.py startapp learning_logs
		Creates infrastructure to build app
		New folder Learning_logs created :
			Models.py : Used to define models
			Views.py : 
			Admin.py : Used to mange users and group, and add models to be managed
Run server (test)
	python manage.py runserver

Define models
	Open models.py
	Class Topics(models.Model):
		Text = models.Charfield(max_length=200)
		We have created a class 'Topic' inherited by 'Models' a parent class to define basic functionality of a model
	
	We then have to add the app name in Settings.py
	Tell python to modify the database with the model (terminal):
		python manage.py makemigrations learning_logs
	Apply migration :
		python manage.py migrate
		
	***Whenever we want to modify the data that Learning Log manages,
	well follow these three steps: modify models.py, call makemigrations on
	learning_logs, and tell Django to migrate the project.

Create SuperUser for admin site:
	python manage.py createsuperuser (terminal)

Django Shell (to explore the data in the database)
	python manage.py shell (terminal)
	from learning_logs.models import Topic
	topics = Topic.objects.all()
	t = Topic.objects.get(id=1)
	***To get data through a foreign key relationship, you use the lowercase
	name of the related model followed by an underscore and the word set
	t.entry_set.all()
	
	
	

	
	
