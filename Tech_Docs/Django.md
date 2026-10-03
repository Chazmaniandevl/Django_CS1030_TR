
1. Django helpful commands

Activate virtual environment :   
Windows: .\\djvenv\\Scripts\\Activate.ps1  
	Mac: source djvenv/bin/activate  


Activate server:   
Python manage.py runserver  


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


Page Done by : Charlie Hedlund
