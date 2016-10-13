# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

create the app

rails new rails_api -d postgresql --skip-bundle

In the Gemfile add gem to serialize the resources we are going to expose on the api
gem 'active_model_serializers'

cd rails_api
bundle install

Making the api
to make api, we will isolate the api controllers under a separate namespace by making
"api" directory in app/controller directory

mkdir app/controllers/api

we will add this namespace in your routes.rb file
we want our responses to be in json

Rails.application.routes.draw do
  namespace :api, defaults: {format: :json} do
  end
end

we should set version for the api

mkdir app/controllers/api/v1

and modify routes.rb file

Rails.application.routes.draw do
  namespace :api, defaults: {format: :json} do
    namespace :v1 do

    end
  end
end

gem 'devise'
rails g devise:install
rails g devise User
rails db:create
rails db:migrate

rails g controller users
and move the users_controller file to api/v1

users_controller.rb file should look like

class Api::V1::UsersController < ApplicationController
  respond_to :json

  def show
    respond_with User.find(params[:id])
  end
end

$ rails console

> User.create({email: "example@railsapi.com",password: "12345678",password_confirmation: "12345678"})

rails s

In the new command line tab hit the endpoint to get the data
curl localhost:3000/api/v1/users/1

addon postman tool to chrome to check api

