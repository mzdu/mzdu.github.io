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


sbulime: dbclick and use cmd + d to select multiple cursors

#### developing note

##### Target:
	Signup
	Post: /api/signup
	creates the user
	
	Update
	PUT: /api/user/:userID
	updates the user
	
	Get
	GET: /api/user/:userID
	gets a specific user

Let's try to figure out how this /api/test works.

1. routes.js 
   server.get(PATH + 'user/:userID', User.getProfile);

   // this creates a url for the service
   // set a get method for /api/test

2. /models/user.js

   // which is associated with mongoose and mongodb using
		var UserSchema = new Schema({
		  user_id: {
				type: String,
				required: true
			},
		  email: {
				type: String,
				unique: true,
				required: true,
			},
		  first_name: String,
		  last_name: String,
		  password: {
				type: String,
				required: true,
			},
		  phone: String,
		  createdDate: { 
		  	type: Date, 
		  	default: Date.now 
		  }	
		});
		mongoose.model('User', UserSchema)
	
   UserSchema defines the structure of User table.

3. /controllers/user.js   create the function to handle the url request
	
	<code>
	exports.getProfile = function(req, res){
		User.find({},function(err, results) {
		
		    return res.send(results);
		  
		  });
	</code>
	
4. Lesson learned, always check your models schema

5. Use findOneAndUpdate to update the user profile.
<code>
	exports.updateProfile = function(req, res){
		
		var query = req.params.userID;
		var update = req.body;
		
		User.findOneAndUpdate(query, update, function(err, data){
			if(err){
				console.log('err is:', err);
				return next(err);
			}
			else{
				console.log('updated');
				return res.send(201, data);
			}
		});
	};
</code>

6. res.send(500, err); must be added.

bkraider  test

### req.params  VS req.body
req.params.user_name accepts the value from variables.

req.body.user_name finds out the value from the json package.

### Signin error
<code>
exports.Login = function(req, res){
	userName = req.body.user_name;	
	
    User.findOne({user_name:userName}, function(err, data){
    	
    	if(err){
    		console.log('err is: ', err);
    		return res.send(err);
    	}
    	else {
    		userPass = req.body.password;
    		if(data != null && data.password == userPass){
    			return res.send(200, {result: 'true'});
    		}
    		else{
    			return res.send(200, {result: 'false'});
    		}

    	}
</code>