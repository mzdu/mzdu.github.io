---
layout: post
title: "Tech Incubator Meeting Note"
tags: api nodejs
date: May 17, 2015
---
**res.setHeader('Access-Control-Allow-Origin','*');** allows the cross domain client to consume the web services.

PostMan Chrome Extension, JSON format

Wish References User Model
	Wish Schema:

<code>
	//Find all donations from one user
	exports.findDonationsFromUser = function(req, res){
	  Donation
	  .find({_donor: req.params.userID})
	  .populate('_donor', 'user_name')
//	  .populate('_charity', 'name')
	  .exec(function(err, results) {
	    if(err){
	      console.log(err);
	    }else{
	      return res.send(results);
	    }
  });
};
</code>