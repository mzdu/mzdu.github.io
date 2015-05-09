---
layout: post
title: "Columbia Incubator Debris"
tags: terminal 
date: May 9, 2015
---
#### How to add the read write permissions recursively?
1. identify your role
> whoami
> id

2. add permissions for that user
> sudo chown -R mzdu:staff ~/Workspace

add read and write permissions
>chmod -R ug+rw foldername