# Deployment of a Unicorned Rails App

## The Unicorn Service Init Script
* The service script is at ``/etc/init.d/unicorned-rails-app``
* Configuration options are set in the upper section of this file
* The Rails App is in ``$RAILS_APP_FOLDER`` e.g. ``/srv/apps/railsapp``
* The Unicorn Server is owned by the ``$USER`` e.g. ``unicorn``
* The Rails Environment is specified in ``$RAILS_ENV`` e.g. ``production``

Make the script executable
* ``sudo chmod +x /etc/init.d/unicorned-rails-app``
Setup the script to be run on 
* ``sudo update-rc.d unicorned-rails-app defaults``

## Rails App Setup
* The Unicorn config script is located at ``$RAILS_APP_FOLDER/config/unicorn.rb``
* The Environment Specific Shell Setup is located at ``$RAILS_APP_FOLDER/init/$RAILS_ENV.env``

## NGINX Setup
* ``apt-get install nginx`` - Creates an nginx service script

## Starting Services
* ``sudo service unicorned-rails-app status``
* ``sudo service nginx status``

