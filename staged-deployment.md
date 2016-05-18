# Staged Deployment

## Local Setup

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

## Git

Initialize repo

    $ git init
    $ git add (see options)
    $ git commit -m "First commit"

Create development branch and push to development branch

    $ git checkout -b development
    $ git push origin development

Merge development branch into master branch, push to master branch

    $ git checkout master
    $ git merge development
    $ git push origin master

## Heroku Deployment

    Create a free Heroku account, if needed: https://signup.heroku.com/www-home-top
    Install Heroku Toolbelt, if needed: https://toolbelt.heroku.com

Authenticate Heroku Account via Terminal

    $ heroku login

Getting Started

    Enter your Heroku credentials.
    Email: your@email.com
    Password (typing will be hidden):
    Authentication successful.

Add Public Key (if needed)

    $ heroku keys:add

Init and Commit ???????????

    $ git init
    $ git add (see options)
    $ git commit -m "Initial commit" (or other message)

Create Heroku app

    $ heroku create app-name

Deploy to Heroku

    $ git push heroku master 

## Staging

URL

    https://reinhardt-family-reunion-staging.herokuapp.com

## Production

URL

    https://reinhardt-family-reunion.herokuapp.com
