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
