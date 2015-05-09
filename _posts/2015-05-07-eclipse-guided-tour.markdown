---
layout: post
title: "Incubator Meeting"
tags: terminal directory permissions
date: May 9, 2015
---
#### How to add the read write permissions recursively?
1. identify yourself

	\>whoami
	
	\>id

2. add permissions for usera

	\> sudo chown -R usera:staff ~/Workspace

	\> sudo chown -R usera:staff /Users/usera

3. add read and write permissions

	\>chmod -R ug+rw foldername

#### developing related

nodemon

http://localhost:8080/api/test  response a json object success.

http://www.evernote.com/l/AZL97NJX1lhNp5y2mfWrTYAQa2AugmPGmvM/

####When you create a new API, you need to:
1. Create a new model file if it doesn’t already exist.
2. Add a new controller for the model or update the existing one with the needed functions.
3. Bind the controller method to the URL you want the API to be consumed from in routes.js
4. Test the endpoint by using Postman or Advanced Rest Client at the URl you specified. For this, you will need to go to terminal at the CharaSparkAPI folder and run ‘nodemon server’. If you don’t have nodemon, you can install it by running ‘sudo npm install -g nodemon’.


dbclick and use cmd + d to select multiple cursors