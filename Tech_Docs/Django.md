
1. Django helpful commands

Activate virtual environment :   
Windows: .\\djvenv\\Scripts\\Activate.ps1  
Mac: source djvenv/bin/activate  
type *deactivate* into console to close out of the virtual environment

Activate server :   
	Python manage.py runserver

Server will run  [Here](http://127.0.0.1:8000/)	

Admin Access is [Here](http://127.0.0.1:8000/admin/)	

Press ctr + break (windows)/ command + c (mac) to exit server

2. Installing Django and Virtual environment

Check your python version:  
	Windows: py \--version  
	Mac : python3 \--version  
Remember this for your django installation  

For django installation you can make sure your python version is compatible [Here](https://docs.djangoproject.com/en/6.1/faq/install/#faq-python-version-support)

Create and enter your portfolio directory. For example:  
mkdir django-portfolio  
cd django-portfolio

Initialize the directory as a local Git repository:  
git init

Create a .gitignore file in VS Code and add:

djvenv/  
\_\_pycache\_\_/  
.DS\_Store

Create your python virtual environment 

### Windows

py \-m venv djvenv

### macOS

python3 \-m venv djvenv

Now activate the environment 

**Windows — PowerShell**  
Enter:  
.\\djvenv\\Scripts\\Activate.ps1

If PowerShell reports that running scripts is disabled, enter:  
Set-ExecutionPolicy \-ExecutionPolicy Bypass \-Scope Process

Then activate the environment again

Mac:   
source djvenv/bin/activate  
There should be a green (djvenv) on your command line now  
![][image1]

Remember your python version and what django version you should be installing  [Here](https://docs.djangoproject.com/en/6.1/faq/install/#faq-python-version-support)

Run :  
	Python \-m pip install django (Mac it may need to be python3)  
	  
Confirm django version with:  
	python \-m django \--version


PORTFOLIO APP CMMNDS

*for other files replace "portfolio_app" with the name of your app*

Checks the status of your project

	python manage.py check 

Creates the app folders for your portfolio app

	python manage.py startapp portfolio_app

Makes your models ready to be moved into spreadsheets

	python manage.py makemigrations portfolio_app

Makes those models into a table in the database

	python manage.py migrate 

Create an admin account

	python manage.py createsuperuser


Page Done by : Charlie Hedlund
