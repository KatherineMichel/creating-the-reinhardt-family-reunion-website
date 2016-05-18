# Staged Deployment Example

## Example Instructions

### Create Project Locally and Push to GitHub master branch

Instructions based on [Pinax Quick Start](http://pinaxproject.com/pinax/quick_start)

Create a GitHub repo and clone locally, but do not cd into the directory. 

    $ git clone https://github.com/KatherineMichel/reinhardt-family-reunion-website

Python, pip, and Django should be installed globally, as well as Heroku Toolbelt installed and authenticated. Run this command in the parent directory:

    $ django-admin startproject --template=https://github.com/pinax/pinax-starter-projects/zipball/static reinhardtfamilyreunion reinhardt-family-reunion-website -n webpack.config.js

Change directory

    $ cd reinhardt-family-reunion-website

At this point, it's strongly recommended that you create and activate a virtualenv of some type. 

    $ pyenv global 3.5.0
    $ pyenv virtualenv reinhardt-family-reunion-website
    $ pyenv activate reinhardt-family-reunion-website

Install requirements, and run server 

    $ pip install -r requirements.txt
    $ chmod +x manage.py

Migrate and runserver

    $ ./manage.py migrate
    $ ./manage.py loaddata sites
    $ ./manage.py runserver
    
Check that the Django welcome page appears

    http://127.0.0.1:8000

Add and commit files

    $ git add -A
    $ git commit -m "Message"

Push to GitHub master branch

    $ git push origin master

## Prepare for Heroku Deployment (Incomplete)

Based on [Pinax Deploying to Heroku](http://pinaxproject.com/pinax/how-tos/deploy-to-heroku)

Add to Requirements

    django-toolbelt

Create Procfile

    web: gunicorn --log-file - mysite.wsgi

Alter wsgi.py

    from dj_static import Cling, MediaCling
    application = Cling(MediaCling(get_wsgi_application()))

## Deploy to Heroku Staging and Production Websites

    $ heroku create app-name
    $ git push heroku master

Migrate and Open Heroku App in Browser

    $ heroku run python manage.py migrate
    $ heroku open 

Fork the App

    $ heroku fork --from app-name --to app-name-staging

Add Forked Remote

    $ heroku info -a app-name-staging
    $ git remote add forked git@heroku.com:app-name-staging.git (or otherwise use Git URL from previous info command)

Alternatively 

    $ git remote add forked https://git.heroku.com/app-named-staging.git

Open Staging or Production Sites in Browser

    $ heroku open --app app-name
    $ heroku open --remote forked

Create local development Branch, Push to Staging Site, Create/Push to GitHub development Branch

    $ git checkout -b development 
    $ heroku keys:add (if needed due to publickeys error)
    $ git push forked master
    $ git push origin development

## Staging and Production Sites

Staging URL

    https://reinhardt-family-reunion-staging.herokuapp.com

Production URL

    https://reinhardt-family-reunion.herokuapp.com

### Merge Changes Between development and master Branches, Push and Pull Between GitHub and Local Branches

Merge changes from development branch into master branch and push to GitHub master branch

    $ git checkout master
    $ git merge development (merge local development branch changes into local master branch)
    $ git push origin master
    $ git push heroku master

Merge changes from master branch into development branch and push to GitHub development branch and Heroku staging site

    $ git checkout development
    $ git merge master (merge local master branch changes into local development branch)
    $ git push origin development
    $ git push forked master

Pull changes (checkout as needed)

    $ git pull origin master
    $ git pull origin development
