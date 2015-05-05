---
layout: post
title: "Rdicount Markdown Syntax"
tags: rdiscount Jekyll
date: May 4, 2015
---

#### Escape ####
Escape: \


#### Headers ####
\# This is an H1 \#

\## This is an H2 \##

\### This is an H3 \###

### Emphasis ###
Italic *

*Italic with star*

Bolded **

** Bolded **

#### Block Quotes ####
\> block quote

#### List ####
  \* Item 1
  \* Item 2
  \* Item 3
  
  * Item 1
  * Item 2
  * Item 3
  
#### Code Style ####
\`print "Hello World"\`

`print "Hello World"`

use [tab]

	def functionA(a, b):
		return a + b
use {hightlight}+%  {endhighlight}+%		
		
{% highlight python %}
def codeA(a,b):
	print a + b
{% endhighlight %}
  
#### Links ####
\[my link text](https://mzdu.github.io)

[my link text](https://mzdu.github.io)

Link Only

<http://mzdu.github.io\> <http://mzdu.github.io>

#### Images ####
\![My image link text]\(https://avatars1.githubusercontent.com/u/1903316?v=3&s=460 =150x50)

![My image link text](https://avatars1.githubusercontent.com/u/1903316?v=3&s=460 =150x50)

#### Centering ####
\-> this will be centered <-

-> this will be centered <-

**Reference**

discount syntax <http://tedwise.com/markdown/>

