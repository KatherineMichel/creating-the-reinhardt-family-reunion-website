# Staged Deployment

The staged deployment process was based on a [Staged Deployment Example](https://github.com/KatherineMichel/staged-deployment-example) that I developed. 

## Details

Create a directory

    $ mkdir reinhardt-family-reunion-website

Run this command in the parent directory, replacing projectname with project name

    $ django-admin.py startproject --template=https://github.com/heroku/heroku-django-template/archive/master.zip --name=Procfile projectname reinhardt-family-reunion-website

Change directory

    $ cd reinhardt-family-reunion-website

At this point, it's strongly recommended that you create and activate a virtualenv of some type. 

## Staging and Production Sites

Production URL

    https://reinhardt-family-reunion.herokuapp.com

Staging URL (the word staging is abbreviated due to 30 character limit)

    https://reinhardt-family-reunion-s.herokuapp.com

