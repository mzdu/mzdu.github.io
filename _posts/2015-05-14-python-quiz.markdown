---
layout: post
title: "Python Quiz Note"
tags: python edx quiz
date: May 14, 2015
---

1. <code>
   print type(1 / 2) 
   
   type 'int'  version 2
   
   type 'float' version 3
   </code>

2. <code>
	def f(): pass

	print type(f())
	
	type 'NoneType'
	</code>
	
3. <code>
	def f(): pass

	print type(f())
	
	type 'NoneType'
	</code>

3. <code>
	print type(1J)
	
	type 'complex'
	</code>

4. <code>
	print type(lambda:None)
	
	type 'function'
	</code>
	
5. <code>
	print len([None, None])
	
	2
	</code>
	
6. <code>
	// lamda expression == anonymous function
	
	d = lambda p: p * 2
	
	t = lambda p: p * 3
	
	x = 2
	
	x = d(x)
	
	x = t(x)
	
	x = d(x)
	
	print x
	
	24
	
	// //
	d = lambda p: p * 2
	=====>
	d = function(p){ return p * 2};
	</code>
	
7. <code>
	x = 4.5
	
	
	y = 2
	
	print x // y
	
	// == floor divide
	
	2.0 
	</code>

8. <code>
	// set
	nums = set([1,1,2,3,3,3,4])

	print len(nums)    // set elements are unique
	
	4
	
	// nums is a set, only unique values are retained.
	// More about set
	
	a = set([1, 2, 3, 4])      //unique letters in a
	
	b = set([2, 4, 5])
	
	a - b ==> set([1, 3])
	
	a | b ==> set([1, 2, 3, 4, 5])
	
	a & b ==> set([2, 4])
	
	a ^ b ==> set([1 ,3 ,5])    //letters in a or b but not in both
	
	// //
	for element in a:

		print element

	1 2 3 4
	
	print a[0]   // set object does not support indexing
	
	1 in a 
	
	True
	
	</code>

9. <code>
	x = True
	
	y = False
	
	z = False
	
	if x or y and z:
	
	    print "yes"
	
	else:
	
	    print "no"
	
	// 'yes', in python, AND is higher precedence than OR
	</code>
	
10. <code>
	If PYTHONPATH is set in the environment, which directories are searched for modules?
	
	A) PYTHONPATH directory

	B) current directory
	
	C) home directory
	
	D) installation dependent default path
	
	A, B and D
	// First is the current directory, then is the PYTHONPATH directory if set, then is the installation dependent default path.
	</code>
	
11. In python 2.6 or earlier, the code will print error type 1 if accessSecureSystem raises an exception of either AccessError type or SecurityError type
	<code>
	
	try:
		accessSecureSystem()

	except AccessError, SecurityError:
  		print "error type 1"

	continueWork()
	
	false // The except statement will only catch exceptions of type AccessError and name the exception object SecurityError. In order to catch both you can use a tuple like this: except (AccessError, SecurityError). Python has been changed in version 3.0 so that the syntax shown in the question will actually catch both types.
	</code>
	
12. <code>
	f = None

	for i in range (5):
    	with open("data.txt", "w") as f:
      	  if i > 2:
            break
	
	True // The WITH statement when used with open file guarantees that the file object is closed when the with block exits.
print f.closed
	</code>
	
13. <code>
	counter = 1 
	
	def doLotsOfStuff():
	    
	    global counter
	
	    for i in (1, 2, 3): 
	        counter += 1
	
	doLotsOfStuff()
	
	print counter
	
	4 // global
	</code>
	
14. <code>
	print "hello" 'world'
	
	helloworld // cancatenated
	</code>
	
15. <code>
	print "\x48\x49!"
	
	HI!   //\x is an escape sequence that means the following 2 digits are a hexadicmal number encoding a character.
	
	print 0xA + 0xa  //0xA and 0xa are both hexadecimal integer literals representing the decimal value 10. There sum is 20.
	</code>

16. <code>
	class parent:
	
    def __init__(self, param):
   
        self.v1 = param

	class child(parent):
	
	    def __init__(self, param):
	
	        self.v2 = param
	
	obj = child(11)
	
	print "%d %d" % (obj.v1, obj.v2)
	
	Error is generated // AttributeError: child instance has no attribute 'v1'. self.v1 was never created as a variable since the parent __init__ was not explicitly called.
	</code>

17. <code>
	values = [1, 2, 1, 3]
	
	nums = set(values)

	def checkit(num):
	
	    if num in nums:
	
	        return True
	
	    else:
	
	        return False
	
	for i in  filter(checkit, values):
	
	    print i
	
	1 2 1 3
	//The filter will return all items from the list values which return True when passed to the function checkit. checkit will check if the value is in the set. Since all the numbers in the set come from the values list, all of the orignal values in the list will return True.
	</code>
	
18. <code>
	values = [2, 3, 2, 4]

	def my_transformation(num):
	    
	    return num ** 2
	
	for i in  map(my_transformation, values):
	    
	    print i
	
	4 9 4 16 
	// map will call the function for each value in the list. The ** operator in the function raises the parameter to the power of 2.
	</code>

19. <code>
	import pickle
	
	class account:

		def __init__(self, id, balance):

			self.id = id

			self.balance = balance

		def deposit(self, amount):

			self.balance += amount

		def withdraw(self, amount):

			self.balance -= amount
	

	myac = account('123', 100)

	myac.deposit(800)

	myac.withdraw(500)
	
	fd = open( "archive", "w" ) 

	pickle.dump( myac, fd)

	fd.close()
	
	myac.deposit(200)

	print myac.balance
	
	fd = open( "archive", "r" ) 

	myac = pickle.load( fd )

	fd.close()

	
	print myac.balance

	600 400  // pickle
	</code>
	
20. <code>
	class Person:
	    def __init__(self, id):
	        self.id = id
	
	obama = Person(100)
	
	obama.__dict__['age'] = 49
	
	print obama.age + len(obama.__dict__)

	51

	We have created a member variable named 'age' by adding it directly the objects dictionary. The value of 'age' is initialized to 49. There are 2 items in the dictionary, 'age' and 'id', therefore the sum of the 'age' value 49 and then size of the dictionary, 2 items, is 51.
	</code>
	
21. <code>
	sys.path.append('/root/mods')
	
	Adds a new directory to search for python modules that are imported.
	
	The list sys.path contains, in order, all the directories to be searched when trying to load a module
	</code>

22. <code>
	import re

	sum = 0
	
	pattern = 'back'

	if re.match(pattern, 'backup.txt'):

	    sum += 1

	if re.match(pattern, 'text.back'):

	    sum += 2

	if re.search(pattern, 'backup.txt'):

	    sum += 4

	if re.search(pattern, 'text.back'):

	    sum += 8
	
	print sum	

	13, search will see if the pattern exists anywhere in the string, while match will only check if the pattern exists in the beginning of the string.
	</code>

23. Assuming the filename for the code below is /usr/lib/python/person.py and the program is run as: 
python /usr/lib/python/person.py 

	What gets printed?

	<code>
	class Person:
    
    def __init__(self):
    
        pass

    def getAge(self):
    
        print __name__

	p = Person()
	
	p.getAge()
	</code>
	
	\__main__
	
	If the module where the reference to \__name\__ is made has been imported from another file, then the module name will be in the variable in the form of the filename without the path or file extension. If the code is being run NOT as the result of an import, the variable will have the special value "\__main\__".
	
24. <code>
	confusion = {}
	
	confusion[1] = 1
	
	confusion['1'] = 2
	
	confusion[1.0] = 4
	
	sum = 0
	
	for k in confusion:
	
	    sum += confusion[k]
	
	print sum
	
	6
	</code>
	
	Note from python docs: "if two numbers compare equal (such as 1 and 1.0) then they can be used interchangeably to index the same dictionary entry. (Note however, that since computers store floating-point numbers as approximations it is usually unwise to use them as dictionary keys.)"
	
25. <code>
	list1 = [0, 2, 4]
	
	list2 = ['a', 'b', 'c']
	
	for sth in (list1, list2):
		
		print sth
		
		print sth[0]
		
	[0, 2, 4]
	
	['a', 'b', 'c']
	
	0, 'a'
	</code>
	

26. <code>
	names1 = ['Amir', 'Barry', 'Chales', 'Dao']

	loc = names1.index("Edward")
	
	print loc
	
	// An exception is thrown
	</code>
	

27. <code>
	tuple.append((1, 2, 3))
	
	tuples are immutable, and do not have append method.
	</code>
	

28. <code>
	def dostuff(param1, *param2):
		print type(param2)

	dostuff('apples', 'bananas', 'cherry', 'dates')
	
	tuple
	</code>
	

29. <code>
	def myfunc(x, y, z, a):

	    print x + y
	
	nums = [1, 2, 3, 4]
	
	myfunc(*nums)	
	
	3, *nums will unpack the list into individual elements to be passed to the function.
	</code>
	

30. How do you create a package so that the following reference will work?
	
	In order to create a package create a directory for the package name and then put an __init__.py file in te directory.
	
31. <code>
	class A:

	    def __init__(self, a, b, c):

	        self.x = a + b + c
	
	a = A(1,2,3)

	b = getattr(a, 'x')

	setattr(a, 'x', b+1)

	print a.x	

	7, getattr can be used to get the value of a member variable of an object. setattr can be used to set it.
	</code>

32. cmp returns a value less than 0 if x is less than y; cmp returns 0 if x equals y; cmp returns a value greater than 0 if x is greater than y.

	x, y = 0, 1
	
	cmp(x, y) ==> -1	

33. <code>
	sum(iterable[, start])
	</code>
	

34. list dict =
	

35. <code>
	dict.copy()  VS  dict.deppcopy()

	dict2 = dict1.copy()
	
	dict1[1] = 100
	
	print dict2[1]
	
	100
	// // // //
	import copy
	
	dict3 = copy.deepcopy(dict1)

	dict1[1] = 100

	dict3[1]
	
	old value
	</code>
	
	or dict3 = dict(dict1)
	
	//created a new dictionary

36. <code>
	kvps = { '1' : 1, '2' : 2 , '3' : 3, '4' : 4, '5' : 5}
	
	newData = { '1' : 10, '3' : 30 }
	
	kvps.update(newData)
	
	x = sum(kvps.values())
	
	print x
	
	51 // update() // sum()
	</code>
	


            