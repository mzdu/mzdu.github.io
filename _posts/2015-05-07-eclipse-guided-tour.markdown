---
layout: post
title: "Columbia Incubator Meeting"
tags: terminal directory permissions
date: May 9, 2015
---
#### How to add the read write permissions recursively?
1. identify yourself
> whoami

> id

2. add permissions for that user
> sudo chown -R mzdu:staff ~/Workspace

> sudo chown -R mzdu:staff /Users/mzdu

add read and write permissions
>chmod -R ug+rw foldername

