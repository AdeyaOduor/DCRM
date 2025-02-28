mkdir djandoCrm
cd djandoCrm
python3 -m venv crmenv
source myenv/bin/activate 
pip install django
pip install mysql-connector
pip install mysql-connector-python3
django-admin startproject djangoCrm

//install mysql on local machine from official website {dev.mysql.com}
cd djangoCrm
python3 manage.py startapp website
code .

 python manage.py makemigrations
 python manage.py migrate
 python manage.py createsuperuser, and enter user and p/word
 python manage.py runserver
       # OR
 python3 ./djangoCrm/manage.py makemigrations
 python3 ./djangoCrm/manage.py migrate
 python3 ./djangoCrm/manage.py createsuperuser, and enter user and p/word
 python3 ./djangoCrm/manage.py runserver

// Git and GitHub CMDs
git config --global user.name "Adeya david"
git config --global user.email "adeyadavid@gmail.com"
git config --global push.default matching
git config --global alias.co checkout
git init
git commit -m "initial commit"








https://github.com/flatplanet/Django-CRM/tree/main/dcrm
