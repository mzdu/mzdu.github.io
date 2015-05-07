---
layout: post
title: "Ruby on Rails P1"
tags: RoR intro configuration
date: May 6, 2015
---
####Getting started

Route = URL + http verb (GET, POST, PUT/PATCH, DELETE)
>GET = find

>POST = add

>PUT/PATCH = update

>DELETE = delete


User1 → Router → CONTROLLER → View → Back to User1

####Starting a Rails Project

1. check your ruby version 
>ruby -v

2. check your rails version 
>rails -v

3. install rails 
>gem install rails

4. start new project 
>rails new projectname

   start rails server
>rails server or rails s

The default url is localhost: 3000, add git tracking for local repo
>git init    
>git add .

Generate controller for rails
>rails generate controller home index

The files generated are saved under 
/app/views/home

index.html.erb <----> /config/locales/routes.rb
  
localhost: 3000/home/index   ←→   get ‘home/index’

set home/index as root and create about page
routes.rb
Rails.application.routes.draw do
  
  root 'home#index'

  get '/about' => 'home#about'
  
2. set home_controller.rb
  def about
  end
  
3. add about.html.erb file under home directory


####Outline of Ruby Study

P1. Introduction and configuration of Ruby on Rails

P2. Models and Migrations

P3. Action Mailer and Active Job

P4. Basics of the Asset PipelineP

P5. Deployment 
