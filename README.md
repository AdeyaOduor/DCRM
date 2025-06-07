mkdir /c/dcrm,
cd /c/dcrm,
python3 -m venv crmenv,
source crmenv/scripts/activate, 
pip install django.

# install mysql on local machine from official website {dev.mysql.com}
pip install mysql-connector,
pip install mysql-connector-python3,

django-admin startproject dcrm.

cd dcrm/
python3 manage.py startapp website
code .

# Edit dcrm/setings.py
add the new app - websites under Apps, and update mysql credentials in DATABASES under settings
INSTALLED_APPS = [
    ...
    'website',
    
DATABASES = {
    'default':{
        'ENGINE': 'django.db.backend.mysql',
        'NAME': '<db_name>',
        'USER': <'root'>,
        'PASSWORD': <'db_password'>,
        'HOST': <'localhost'>,
        'PORT': <'db_port'>
    }
}
    ....
    ALLOWED_HOSTS =[]
    
    LOGIN_URL = '/login/'
    LOGIN_REDIRECT_URL = '/'
    LOGOUT_REDIRECT_URL = '/'
    
    STATIC_URL = 'static/'
    STATIC_URL = 'media/'
    MEDIA_ROOT = BASE_DIR / 'media' # creates media folder inside the root
]
--------------------------------------------------------------------------------
# create mydb.py file (touch mydb.py in editor terminal)

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
set ssh key - Learn how to in git
git config --global user.name "Adeya david"
git config --global user.email "adeyadavid@gmail.com"
git config --global push.default matching
git config --global alias.co checkout


go to github, set a repository and use push command for an existing repo and refresh

# in editor terminal
add files under website
create template folder in website and its files

git init 
git add . 
git commit -m "initial commit"

python manage.py makemigrations 
python manage.py migrate python manage.py 

python manage.py runserver
 # OR 
 python3 ./dcrm/manage.py makemigrations 
 python3 ./dcrm/manage.py migrate 
 python3 ./dcrm/manage.py runserver

# carousel_base.html
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>{% block title %}My Django CRM{% endblock %}</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
    <style>
        .carousel-item {
            height: 100vh; /* Full viewport height */
        }
        .carousel-item img {
            object-fit: cover; /* Cover the entire area */
            width: 100%; /* Full width */
            height: 100%; /* Full height */
        }
        .content {
            position: relative;
            z-index: 1; /* Ensure content is above the carousel */
            color: white; /* Change text color for visibility */
            padding: 2rem; /* Add padding for content */
        }
        footer {
            background-color: #f8f9fa; /* Light background for footer */
            padding: 1rem 0; /* Padding for footer */
        }
    </style>
    {% block extra_head %}{% endblock %}
</head>
<body>
    {% include 'navbar.html' %}
    
    <div id="imageCarousel" class="carousel slide" data-bs-ride="carousel" data-bs-interval="4000">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src="{% static 'images/image1.jpg' %}" alt="Image 1">
            </div>
            <div class="carousel-item">
                <img src="{% static 'images/image2.jpg' %}" alt="Image 2">
            </div>
            <div class="carousel-item">
                <img src="{% static 'images/image3.jpg' %}" alt="Image 3">
            </div>
        </div>
        
        <button class="carousel-control-prev" type="button" data-bs-target="#imageCarousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#imageCarousel" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>

    <div class="container content">
        <br/>
        {% if messages %}
            {% for message in messages %}
                <div class="alert alert-warning alert-dismissible fade show" role="alert">
                    {{ message }}
                    <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
                </div>
            {% endfor %}
        {% endif %}
        
        {% block content %}
        <h1>Welcome to My Django CRM</h1>
        <p>This is where you can add your content.</p>
        {% endblock %}
    </div>

    <footer>
        <div class="container text-center">
            <p>© 2025 My Django CRM</p>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js" integrity="sha384-w76AqPfDkMBDXo30jS1Sgez6pr3x5MlQ1ZAGC+nuZB+EYdgRZgiwxhTBTkF7CXvN" crossorigin="anonymous"></script>
</body>
</html>
