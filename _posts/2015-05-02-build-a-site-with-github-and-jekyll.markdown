---
layout: post
title: "Build a Site with Github and Jekyll"
date: May 2, 2015
---

1. Introduction
Intro
About Jekyll
Steps:
install jekyll locally
launch the server locally
after editing your stuff, upload it to the github

2.What We are building
Example, News from London
with Title, content, page

click and check the detail of article, with news archive
with RSS feedsite

3.Installing Jekyll
requirements:
1.ruby
2.ruby gems, is a packaging system for ruby.
3. Unix, Linux, OS

install jekyll 
> sudo gem install jekyll
> sudo gem install rdiscount     (for markdown package)

4.How Jekyll Works
yaml configuration
_config.yml

pretty much like angularJS or any other modern front-end templates

5.Configuring the site
create a new project for jekyll

create a new site
> jekyll new myJsite            which creates a site template


start the local server
> jekyll serve                       starts the template, which enables jekyll to translate the variables in static html page to the final static html page.
running on http://127.0.0.1:4000/

download the code from mijingo.com/code

File Directory
_site
_posts     where posts are
   
_config.yml

=================


layout: post
title: Henry's Statement
date: September 20, 1880


--- three dashes means the yaml content





What is a YAML file?
Human-friendly data serialization standard
popular with Python and Ruby on Rails project
with 
key: value format

yaml.org  to check specificaitons

// Site settings
title: "My Site"
email: daniel_pub@hotmail.com
description: "A memory storage."
baseurl: "" # the subpath of your site, e.g. /blog/
url: "http://localhost:4000" # the base hostname & protocol for your site
github_username:  mzdu

// Build settings
markdown: rdiscount
rdiscount: 
	extensions: [smart]
permalink: /articles/:title





6.Building the templates
_layouts

copy default.html from resource


learning liquid
like google app engine 

{% for sth in sssss %}

{{ sth }}

{% endfor %}

Building the Homepage



7.Deploying to Github Pages
sftp
via git
beanstalk
and so on

on Github


In order to run the complete template
> run jekyll serve --baseurl ‘’
