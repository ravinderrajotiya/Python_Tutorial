# Python_Tutorial
Django Tutorial
#Install Django as 
c:/> pip install django
#install django environment
c:/> pip install virtualEnv
#download ATOM from www.atom.io and install ATOM - 
#now Create a project folder
c:/> mkdir project
c:/project> django-admin startproject myProject
	#django will create a project and will have following in it
	#manage.py
	#myFolder with number of python files such as urls.py, settings.py....
#now runserver
c:/project/myProject> python manage.py runserver
	#this will run the server and also give url address 
	#copy this url 128.0.0.1:8000/ in the browser and click enter
	#django server will start with congratulation message
#You must have installed ATOM
#open the project – myProject in ATOM
#and
right click myProject (inner flder) and create new file views.py as follows 
views.py
	from django.shortcuts import render
	def home(request):
	    return  render(request,"index.html")
	def about(request):
	    return render(request, "about.html")
urls.py         # already build by django in project folder
		# add path of functions
	from . import views
	urlpatterns = [
	    path('admin/', admin.site.urls),
	    path('', views.home),
	    path('about/', views.about),
	]

create a folder template in your main project folder
Goto settings.py in the project through IDE (ATOM) sftware and edit in DIR=[‘template’] and save
right click and creat new files index.html and about.html
	# edit and write some thing in these files
Now you can open the pages built in the browser
# Project Create a static webpage using html, css
**Static website steps**

create a folder
create a subfolder project name
change to this directory
#start project
c:/> django-admin startproject staticWeb
change to this directory
c:/staticWeb> python manage.py runserver
copy url in the browser address bar and click enter
	# this will open page displaying django server started successfully

Now open atom
go to file and click open folder, browse the folder containing the project “staticWeb’
1. create views.py
	from django.shortcuts import render
	def home(request):
	    return render(request,'index.html')
2. edit urls.py
	from . import views
	urlpatterns = [
    		path('admin/', admin.site.urls),
    		path('', views.home, name='home'),
3. create template folder in outer main project folder and
	a. open settings.py and edit DIR = [‘template’] and save this file
	b. create a new file index.html inside template folder as
		<!DOCTYPE html>
		<html lang="en" dir="ltr">
		<head>
		<meta charset="utf-8">
    		<title>home</title>
    
		</head>
  		<body>
  			  <h1> this is home page </h1>
  		</body>
		</html>
4. create a folder ‘static’ in the outer main project folder
	4a.	create ccs file main.css inside static folder as:
		body{
		  	background-color: blue;
		}
	4b.	open settings.py and edit at the end as:
		# Static files (CSS, JavaScript, Images)
		# https://docs.djangoproject.com/en/3.0/howto/static-files/
		import os.path
		#STATIC_URL = '/static/'                     #already there don’t do anything to this line
		STATICFILES_DIRS=(os.path.join('static'),)

		clck save (or CTRL-s) settings.py
5. Now goto index.html file and add following in <head>    </head> tag
	<head>
    	<meta charset="utf-8">
    	<title>home</title>
    		{%load static%}
    		<link rel="stylesheet" href={% static 'main.css'%}
  	</head>

6. the index.html file now look as given below:
	<!DOCTYPE html>
	<html lang="en" dir="ltr">
  	<head>
    		<meta charset="utf-8">
    		<title>home</title>
    		{%load static%}
    		<link rel="stylesheet" href={% static 'main.css'%}
  	</head>
  	<body>
    		<h1> this is home page </h1>
  	</body>
	</html>
7.	now goto browser and refresh and you will notice
 		home page with blue background
