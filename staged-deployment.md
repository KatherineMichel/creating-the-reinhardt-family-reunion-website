# Staged Deployment

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
