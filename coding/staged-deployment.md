# Staged Deployment

Created using [Staged Deployment Example](https://github.com/KatherineMichel/staged-deployment-example)

## Details

Repo Name

    $ git clone https://github.com/KatherineMichel/reinhardt-family-reunion-website

Python, pip, and Django should be installed globally, as well as Heroku Toolbelt installed and authenticated. Run this command in the parent directory:

    $ django-admin startproject --template=https://github.com/pinax/pinax-starter-projects/zipball/static reinhardtfamilyreunion reinhardt-family-reunion-website -n webpack.config.js

Change directory

    $ cd reinhardt-family-reunion-website

At this point, it's strongly recommended that you create and activate a virtualenv of some type. 

    $ pyenv global 3.5.0
    $ pyenv virtualenv reinhardt-family-reunion-website
    $ pyenv activate reinhardt-family-reunion-website

## Staging and Production Sites

Production URL

    https://reinhardt-family-reunion.herokuapp.com

Staging URL (the word staging is abbreviated due to 30 character limit)

    https://reinhardt-family-reunion-s.herokuapp.com

