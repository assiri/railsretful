# SIMPLE RAILS 5 REST API

Example of a basic REST API to perform CRUD functions. Uses Sqlie3  & rails new railsresful --api

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
## ArticlesController
```bash
class ArticlesController < ApplicationController
      def index
        articles = Article.order('created_at DESC');
        render json: {status: 'SUCCESS', message:'Loaded articles', data:articles},status: :ok
      end

      def show
        article = Article.find(params[:id])
        render json: {status: 'SUCCESS', message:'Loaded article', data:article},status: :ok
      end

      def create
        article = Article.new(article_params)

        if article.save
          render json: {status: 'SUCCESS', message:'Saved article', data:article},status: :ok
        else
          render json: {status: 'ERROR', message:'Article not saved', data:article.errors},status: :unprocessable_entity
        end
      end

      def destroy
        article = Article.find(params[:id])
        article.destroy
        render json: {status: 'SUCCESS', message:'Deleted article', data:article},status: :ok
      end

      def update
        article = Article.find(params[:id])
        if article.update_attributes(article_params)
          render json: {status: 'SUCCESS', message:'Updated article', data:article},status: :ok
        else
          render json: {status: 'ERROR', message:'Article not updated', data:article.errors},status: :unprocessable_entity
        end
      end

      private

      def article_params
        params.permit(:title, :body)
      end
    end
```
## GO
```bash
http://localhost:3000/api/v1/articles
```
## RESTful
```bash
GET    /api/v1/articles
POST   /api/v1/articles     ~ api/v1/articles#create
GET    /api/v1/articles/:id ~ api/v1/articles#show
PATCH  /api/v1/articles/:id ~ api/v1/articles#update
PUT    /api/v1/articles/:id  ~ api/v1/articles#update
DELETE /api/v1/articles/:id ~ api/v1/articles#destroy
```
