# Manipulating Strings
- A raw string completely ignores all escape characters and prints any backslash that appears in the string. `print(r'That is Carol\'s cat.')` -- > `That is Carol\'s cat.`
 - Functions : 
	 - There are The `upper(), lower(), isupper(), and islower()` String Methods.Nonletter characters in the string remain unchanged. 
	- The `isupper()` and `islower()` methods will return a Boolean `True` value if the string has at least one letter and all the letters are uppercase or lowercase, respectively. Otherwise, the method returns `False`.
	- `isalpha()` returns True if the string consists only of letters and is not blank.
	- `isalnum()` returns True if the string consists only of letters and numbers and is not blank.
	- `isdecimal()` returns True if the string consists only of numeric characters and is not blank.
	- `isspace()` returns True if the string consists only of spaces, tabs, and newlines and is not blank.
	- `istitle()` returns True if the string consists only of words that begin with an uppercase letter followed by only lowercase letters.

	- The `startswith()` and `endswith()` methods return `True` if the string value they are called on begins or ends (respectively) with the string passed to the method; otherwise, they return `False`.
	- The `join()` method is useful when you have a list of strings that need to be joined together into a single string value.
		- `', '.join(['cats', 'rats', 'bats'])`
	- The split() method does the opposite: It’s called on a string value and returns a list of strings.
		- `'My name is Simon'.split()` - > `['My', 'name', 'is', 'Simon']`
		- By default, the string 'My name is Simon' is split wherever whitespace characters such as the space, tab, or newline characters are found.
		- The rjust() and ljust() string methods return a padded version of the string they are called on, with spaces inserted to justify the text. The first argument to both methods is an integer length for the justified string. 
			- `'Hello'.rjust(20, '*')`  - > `'***************Hello'`
	- Removing Whitespace with `strip()`, `rstrip()`, and `lstrip()`
		- The strip() string method will return a new string without any whitespace characters at the beginning or end. The `lstrip()` and `rstrip()` methods will remove whitespace characters from the left and right ends, respectively. 
 
	- **Project**
		- Password Locker
			

				import pyperclip
				import sys

				PASSWORDS = {'email': 'F7minlBDDuvMJuxESSKHFhTxFtjVB6',
				'blog': 'VmALvQyKAxiVH5G8v01if1MLZF3sdt',
				'luggage': '12345'}


				if len(sys.argv)<2:
				    print ("Format")
   				sys.exit()

				account = sys.argv[1]

				if account in PASSWORDS.keys():
				    pyperclip.copy(PASSWORDS[account])
   				print("Password Copied")
				else:
    				print("No Account")


		
	 - **Practice Questions**
	 	1. What are escape characters?
			- '\' required to interpret the character in strings in a way they are.
		2. What do the \n and \t escape characters represent?
			- New line and tab.
		3. How can you put a \ backslash character in a string?
			- `\\`
		4. The string value "Howl's Moving Castle" is a valid string. Why isn’t it a problem that the single quote character in the word Howl's isn’t escaped?  
			- Because double quotes are use which doesn't need to escape single quotes between them.
		5. If you don’t want to put \n in your string, how can you write a string with newlines in it?
			- Triple quotes
		6. What do the following expressions evaluate to?

				• 'Hello world!'[1] - e
				• 'Hello world!'[0:5] - Hello
				• 'Hello world!'[:5] - world
				• 'Hello world!'[3:] - lo world!
	 
		7. What do the following expressions evaluate to?

				• 'Hello'.upper() - HELLO
				• 'Hello'.upper().isupper()  - True
				• 'Hello'.upper().lower() - hello

		8. What do the following expressions evaluate to?

				• 'Remember, remember, the fifth of November.'.split() - ['Remember,'remember,','the','fifth','of','November.']
				• '-'.join('There can be only one.'.split()) - 'There-can-be-only-one.'
		
		9. What string methods can you use to right-justify, left-justify, and center a string?
			- right-justify : rjust()
			- left-justify : ljust() 
			- center - center()
		
		10. How can you trim whitespace characters from the beginning or end of a string?
			- lstrip()
			- rstrip()
		

		- **Practice Project**
			
				tableData = [['apples', 'oranges', 'cherries', 'banana'],
 				['Alice', 'Bob', 'Carol', 'David'],
 				['dogs', 'cats', 'moose', 'goose']]


				tableData =  zip(*tableData)

				for i in range(len(tableData)):
			    print ' '.join(tableData[i])


