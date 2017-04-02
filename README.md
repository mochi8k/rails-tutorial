# rails-tutorial

## Docker
```
$ docker-compose run web rails new . --force --database=mysql --skip-bundle
$ docker-compose build
$ docker-compose run web rake db:create
$ docker-compose up
```

## Rails
```
$ bundle install --without production
$ rails db:migrate
$ rails test
$ rails server
```
