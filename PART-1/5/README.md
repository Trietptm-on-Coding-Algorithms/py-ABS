# Dictionaries and Structuring Data

 - Indexes for dictionaries are called keys
 - Unlike lists, items in dictionaries are unordered. The first item in a list named spam would be spam[0]. But there is no “first” item in a dictionary. 

			birthdays ={}
			birthdays[name] = bday

 - There are three dictionary methods that will return list-like values of the dictionary’s `keys`, `values`, or `both keys and values`: `keys()`, `values()`, and `items()`. 
 - The values returned by these methods are not true lists: They cannot be modified and do not have an append() method. But these data types (dict_keys, dict_values, and dict_items, respectively) can be used in for loops. [tuples]
 - If you want a true list from one of these methods, pass its list-like return value to the list() function. `list(dict_keys(1,2))`
		 
 - You can also use the multiple assignment trick in a for loop to assign the key and value to separate variables. `for i,j in di.keys():`
 - It’s tedious to check whether a key exists in a dictionary before accessing that key’s value. Fortunately, dictionaries have a get() method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key does not exist.
		`'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'`

 - You’ll often have to set a value in a dictionary for a certain key only if that key does not already have a value. The `setdefault()` method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key does not exist. If the key does exist, the `setdefault()` method returns the key’s value. 
		
		`spam.setdefault('color', 'black')`


- Tic Tac Toe in python
 
		board = {'T1':'','T2':'','T3':'','M1':'','M2':'','M3':'','B1':'','B2':'','B3':''}

		def setboard(theboard):

		    print(theboard['T1'] + ' | ' + theboard['T2'] + ' | ' + theboard['T3'] )
		    print(theboard['M1'] + ' | ' + theboard['M2'] + ' | ' + theboard['M3'] )
		    print(theboard['B1'] + ' | ' + theboard['B2'] + ' | ' + theboard['B3'] )


		turn = 'X'
		for i in range(9):
    		setboard(board)
    		print("It's " +  turn + " !" )
    		move = raw_input()
    		board[move] = turn
    		if turn == "X":
        		turn = "O"
    		else:
        		turn = "X"
    		print setboard(board)


 - **Practice Questions**
	1. What does the code for an empty dictionary look like?
		- {}
	2. What does a dictionary value with a key 'foo' and a value 42 look like?
		- {'foo':42}
	3. What is the main difference between a dictionary and a list?
		- List is an ordered array while dictionary is unordered.
	4. What happens if you try to access spam['foo'] if spam is {'bar': 100}?
		- KeyError
	5. If a dictionary is stored in spam, what is the difference between the expressions 'cat' in spam and 'cat' in spam.keys()?
		- No Difference
	6. What is a shortcut for the following code?
	
			if 'color' not in spam:
				 spam['color'] = 'black'

		- `spam.setdefault("color","black")`
