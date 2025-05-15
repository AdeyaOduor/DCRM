mkdir /c/dcrm,
cd /c/dcrm,
python3 -m venv crmenv,
source crmenv/scripts/activate, 
pip install django.
pip install mysql-connector,
pip install mysql-connector-python3,
# install mysql on local machine from official website {dev.mysql.com}

django-admin startproject dcrm.

cd dcrm/
python3 manage.py startapp website
code .

# Edit dcrm/setings.py
add the new app - websites under Apps, and update mysql credentials in DATABASES under settings

 python manage.py makemigrations
 python manage.py migrate
 python manage.py createsuperuser, and enter user and p/word
 python manage.py runserver
       # OR
 python3 ./djangoCrm/manage.py makemigrations
 python3 ./djangoCrm/manage.py migrate
 python3 ./djangoCrm/manage.py createsuperuser, and enter user and p/word
 python3 ./djangoCrm/manage.py runserver

# Git and GitHub CMDs
git config --global user.name "Adeya david"
git config --global user.email "adeyadavid@gmail.com"
git config --global push.default matching
git config --global alias.co checkout
git init
git commit -m "initial commit"
