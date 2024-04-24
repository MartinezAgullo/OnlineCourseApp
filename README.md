This repository is the assignment of the IBM course [Develope applications with Django](https://www.coursera.org/learn/developing-applications-with-sql-databases-and-django).  

**General Notes**

An `onlinecourse` app has already been provided in this repo upon which you will be adding a new assesement feature.

- If you want to develop the final project on Theia hosted by [IBM Developer Skills Network](https://labs.cognitiveclass.ai/), you will need to create the same project structure on Theia workspace and save it everytime you close the browser
- Or you could develop the final project locally by setting up your own Python runtime and IDE
- Hints for the final project are left on source code files
- You may choose any cloud platform for deployment (default is IBM Cloud Foundry)
- Depends on your deployment, you may choose any SQL database Django supported such as SQLite3, PostgreSQL, and MySQL (default is SQLite3)

**ER Diagram**
For your reference, we have prepared the ER diagram design for the new assesement feature.

![Onlinecourse ER Diagram](https://github.com/ibm-developer-skills-network/final-cloud-app-with-database/blob/master/static/media/course_images/onlinecourse_app_er.png)



# How to

## Set up
Download the code from

>         [ ! -d 'tfjzl-final-cloud-app-with-database' ] && git clone https://github.com/ibm-developer-skills-network/tfjzl-final-cloud-app-with-database.git
>         cd tfjzl-final-cloud-app-with-database

  
set up the virtual environment

>         pip install --upgrade distro-info
>         pip3 install --upgrade pip==23.2.1    
>         pip install virtualenv
>         virtualenv djangoenv 
>         source djangoenv/bin/activate
>         pip install -U -r requirements.txt


## Migrations
Used by Django for change propagation into the models.

- migrate: Apply/unapply migrations
- makemigrations: Create new migrations based on the changes made into the models.
- sqlmigrate: Displays SQL statement for a migration
- showmigrations: Lists the migrations and status of a project
  
Do:
> python3 manage.py makemigrations onlinecourse 
> python3 manage.py migrate

Note: If you see any errors related to model migrations, you could delete the existing database `db.sqlite3` and rerun the above migration again.

## Web server
To run the web server do:
> python3 manage.py runserver
 
Web server in http://127.0.0.1:8000/ .
 To launch normally go to:
  https://pablomarti12-8000.theianext-1-labs-prod-misc-tools-us-east-0.proxy.cognitiveclass.ai/onlinecourse

## Create admin
Use:
> python3 manage.py createsuperuser

Set the username to 'admin' and set the password. Then, to launch the web server as admin go to:
 https://pablomarti12-8000.theianext-1-labs-prod-misc-tools-us-east-0.proxy.cognitiveclass.ai/admin