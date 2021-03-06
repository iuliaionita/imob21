# Imob21

## Development Tools
Install homebrew - http://brew.sh/
````
  $ brew install nodejs imagemagick phantomjs
````
Install redis
````
  $ brew install redis
````

## Ruby version
Ruby 2.0.0
````
  $ rvm install 2.0.0
````

## System dependencies
## Postgresql
#### MAC OS
Instalation guides: https://wiki.postgresql.org/wiki/Detailed_installation_guides

#### Ubuntu
````
  $ sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main' > /etc/apt/sources.list.d/pgdg.list"
  $ wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
  $ sudo apt-get update
  $ sudo apt-get install postgresql-common
  $ sudo apt-get install postgresql-9.3 libpq-dev
````

## Configuration

## Database creation
Create postgres user
````
  $ sudo -u postgres createuser user_name -s
````
If you would like to set a password for the user, you can do the following
````
  $ sudo -u postgres psql
  $ postgres=# \password user_name
````

Create database
````
  $ rake db:create
````

## Services (job queues, cache servers, search engines, etc.)
Before running the server locally you need to run redis and sidekiq
Run redis
````
  $ redis-server
````
Run sidekiq
````
  $ bundle exec sidekiq
````
## Deployment

#### Inital Setup:

````
  $ git remote add heroku git@heroku.com:imob21.git
````
#### Deploying

````
  $ git push heroku master
````