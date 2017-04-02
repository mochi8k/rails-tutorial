# rails-tutorial

## Docker
```
$ docker-compose run web rails new . --force --database=mysql --skip-bundle
$ docker-compose build
$ docker-compose run web rake db:create
$ docker-compose up
```

## Vagrant
```
$ cd vagrant
$ vagrant up
$ vagrant ssh
$ bundle install --without production
$ rails db:migrate
$ rails test
$ rails s -p 3000 -b '0.0.0.0'
```
