# Professional Practice Django Folder Structure

## Follow these steps below 

#### 1. Create an `env` file and activate the `env` path. 
```bash 
python -m venv env 
env/Scripts/activate
``` 

#### 2. Install Django and Django REST Framework 
```bash 
pip install django 
pip install djangorestframework 
``` 

#### 3. Start Django-Project 
```bash 
django-admin startproject config . 
```

#### 4. Create apps 
```bash 
mkdir apps 
cd apps 
python ../manage.py startapp app_name
```

