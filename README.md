# README

## rails app in heroku

## Setup heroku

```
brew install heroku/brew/heroku
heroku login # input email address and password
```

## Create Application

```
heroku create APP_NAME
```

or

create in https://dashboard.heroku.com/apps

## Create Database

```
heroku addons:create cleardb:ignite
heroku config | grep CLEARDB_DATABASE_URL # mysql://******
heroku config:set CLEARDB_DATABASE_URL=mysql2://****** # mysql -> mysql"2"
```

or

1. visit https://dashboard.heroku.com/apps/APP_NAME/resources
2. add "ClearDB MySQL Ignite(Free)" in "add-ons"
3. edit CLEARDB_DATABASE_URL mysql://****** -> mysql2://******

## Migration

```
heroku run -a APP_NAME rails db:migrate
```

or

1. visit https://dashboard.heroku.com/apps/APP_NAME/access?web-console=APP_NAME
2. More > Run console
3. heroku run rails db:migrate

## log tailing

```
heroku logs -a APP_NAME --tail
```
