# Coding

## Framework

### Pinax Static Site Project

Instructions based on [Pinax Quick Start](http://pinaxproject.com/pinax/quick_start)

    pyenv global 3.5.0
    git clone https://github.com/KatherineMichel/reinhardt-family-reunion-website
    cd reinhardt-family-reunion-website
    pyenv virtualenv reinhardt-family-reunion-website
    pyenv activate reinhardt-family-reunion-website
    pip install django
    django-admin startproject --template=https://github.com/pinax/pinax-starter-projects/zipball/static reinhardtfamilyreunion -n webpack.config.js
    cd reinhardtfamilyreunion
    pip install -r requirements.txt
    chmod +x manage.py
    ./manage.py migrate
    ./manage.py loaddata sites
    ./manage.py runserver

Based on [Pinax Deploying to Heroku](http://pinaxproject.com/pinax/how-tos/deploy-to-heroku)

Add to Requirements

    python-decouple==3.0
    django-toolbelt

Create Procfile

    web: gunicorn --log-file - mysite.wsgi

Alter wsgi.py

    from dj_static import Cling, MediaCling
    application = Cling(MediaCling(get_wsgi_application()))

Creating a Heroku App

    heroku create app-name

### Pinax Blog App

## CSS and HTML

## JavaScript/jQuery

## Models

## Views
