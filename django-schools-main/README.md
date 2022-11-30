This is an example project to illustrate an implementation of multiple user types. In this Django app, teachers can create quizzes and students can sign up and take quizzes related to their interests.

## Running the Project Locally

First, clone the repository to your local machine:

```bash
git clone https://github.com/Fouedrk/DJANGO-SCHOOLS.git
```

Create Virtual Env and Install the requirements:

```bash
cd django-schools
python3 -m venv env
source ./env/bin/activate
pip install -r requirements.txt
```

Create the database and run the development server:

```bash
cd django_school
cp .env.sample .env # update it
python manage.py migrate
python manage.py loaddata datas.json
python manage.py runserver
```

The project will be available at http://127.0.0.1:8000, Login using::

**Teacher**

+ username: `teacher`
+ password: `teacher`

**Student**

+ username: `student`
+ password: `student`

+ username: `fouedrekik97@gmail.com`
+ password: `1234`


## Deployment

```
$ vim /etc/apache2/sites-available/djangoschools.conf

<VirtualHost *:80>
    ServerName django.stackschools.com

    WSGIDaemonProcess djangoschoolapp python-home=/var/www/django-schools/django_school/env python-path=/var/www/django-schools/django_school
    WSGIProcessGroup djangoschoolapp
    WSGIScriptAlias / /var/www/django-schools/django_school/django_school/wsgi.py
    ErrorLog /var/www/django-schools/error.log
    CustomLog /var/www/django-schools/access.log combined
</VirtualHost>
```


