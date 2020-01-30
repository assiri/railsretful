# SIMPLE RAILS 5 REST API

Example of a basic REST API to perform CRUD functions. Uses Sqli3 by default. Please add your own database and credentials

## INSTALL DEPENDENCIES
```bash
$ bundle install
```

## RUN MIGRATION
```bash
$ rails db:migrate
```
## RUN SEEDS
```bash
$ rails db:seed
```
## RUN SERVER
```bash
$ rails s
```


# GO
```bash
http://localhost:3000/api/v1/articles
```
# RESTful
```bash
GET    /api/v1/articles
POST   /api/v1/articles     ~ api/v1/articles#create
GET    /api/v1/articles/:id ~ api/v1/articles#show
PATCH  /api/v1/articles/:id ~ api/v1/articles#update
PUT    /api/v1/articles/:id  ~ api/v1/articles#update
DELETE /api/v1/articles/:id ~ api/v1/articles#destroy
```
