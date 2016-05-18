# Staged Deployment

## Git

Initialize repo

    $ git init
    $ git commit -m "First commit"

Create development branch and push to development branch

    $ git checkout -b development
    $ git push origin development

Merge development branch into master branch, push to master branch

    $ git checkout master
    $ git merge development
    $ git push origin master

## Heroku

    $ heroko create app-name

## Staging

URL

    https://reinhardt-family-reunion-staging.herokuapp.com

## Production

URL

    https://reinhardt-family-reunion.herokuapp.com
