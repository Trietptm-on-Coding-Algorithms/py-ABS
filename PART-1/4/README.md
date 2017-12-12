# Lists

- Python will give you an `IndexError` error message if you use an index that exceeds the number of values in your list value.
- `Indexes` can be only integer values, not floats. 
- While indexes start at 0 and go up, you can also use negative integers for the index. 
- A `method` is the same thing as a function, except it is “called on” a value. 
-  a string is immutable: It cannot be changed. 
- If you have only one value in your tuple, you can indicate this by placing a trailing comma after the value inside the parentheses. Otherwise, Python will think you’ve just typed a value inside regular parentheses. The comma is what lets Python know this is a tuple value.
- **Practice Questions**

	1. What is []?
	 	- It a List
	
	2. How would you assign the value 'hello' as the third value in a list stored in a variable named spam? (Assume spam contains [2, 4, 6, 8, 10].)
		- `spam[2] = 'hello'`
	
	For the following three questions, let’s say spam contains the list ['a', 'b', 'c', 'd'].
	
	3. What does spam[int('3' * 3. What does spam[int('3' * 2) / 11] evaluate to?
		- `'d'`
	
	4. What does spam[- 4. What does spam[-1] evaluate to?
		- `'d'`
 	
	5. What does spam[:2] evaluate to?
		- `['a','b']`

	For the following three questions, let’s say bacon contains the list [3.14, 'cat', 11, 'cat', True].

	6. What does bacon.index('cat') evaluate to?
		- `1`
 	
	7. What does bacon.append(99) make the list value in bacon look like?
		- `Index out of range`
	
	8. What does bacon.remove('cat') make the list value in bacon look like?
		`[3.14,11, 'cat', True]`
 
	9. What are the operators for list concatenation and list replication?
		`+` and `*`

	10. What is the difference between the append() and insert() list methods?
		- `append` set the value at the last+1 index
		- `insert` set the value indicated in the parameter.
	
	11. What are two ways to remove values from a list?
		- `del`
		- `remove`
	
	12. Name a few ways that list values are similar to string values.
		- 
	13. What is the difference between lists and tuples?
		- Mutability 
	14. How do you type the tuple value that has just the integer value 42 in it?
		- Use comma after the value (42,) or double parenthesis ((42)) 
	15. How can you get the tuple form of a list value? How can you get the list form of a tuple value?
		- tuple(list)
		- list(tuple)
	16. Variables that “contain” list values don’t actually contain lists directly. What do they contain instead?
		- It contains the reference to the values.
	

**Practice Projects**

	#Comma Code
		
			strings=''
			def fun(l):
				for i in range(len(l)-1):
					strings= strings+l[i]+", "
				return strings + 'and ' + l[-1]
			
		
