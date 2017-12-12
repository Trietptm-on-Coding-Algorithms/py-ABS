# Functions
 - `None` represents the absence of a value. `None` is the only value of the NoneType data type. (Other programming languages might call this value `null, nil, or undefined`.) 
 - if you use a `return` statement without a value (that is, just the return keyword by itself), then `None` is returned.
 - `print('Hello', end='')` - The output is printed on a single line because there is no longer a newline printed 
 - If you need to modify a global variable from within a function, use the global statement. 
 - **Practice Question**
	1. Why are functions advantageous to have in your programs?
		- Makes the program more readable and provide code reuseability.
	2. When does the code in a function execute: when the function is defined or when the function is called?
		- When it is called. fun()
	3. What statement creates a function?
		- `def function_name()`
	4. What is the difference between a function and a function call?
		- Defining a function doesn't do anything, calling a function does.
	5. How many global scopes are there in a Python program? How many local scopes?
 		- `global scopes` only one, `local scope` - many.
	6. What happens to variables in a local scope when the function call returns?
		- It gets destroyed after the function returns.
	7. What is a return value? Can a return value be part of an expression?
		- `return` value is the value which is gives back when the function is called, yes it can be an expression.
	8. If a function does not have a return statement, what is the return value of a call to that function?
		- `None`
	9. How can you force a variable in a function to refer to the global variable?
		- Use `global` keyword before the variable.
	10. What is the data type of None?
		- `None`
	11. What does the import areallyourpetsnamederic statement do? 
		- It imports the module in the python code, so we can use the functions and variables defined in it.
	12. If you had a function named bacon() in a module named spam, how would you call it after importing spam?
	 	- spam.bacon()
 	13. How can you prevent a program from crashing when it gets an error?
		- By using `exception` handling - use of `try` and `except`
	14. What goes in the try clause? What goes in the except clause?
		- In `try` clause we put the code that should run and gives the desired result. In `except` we catch the errors.
		

	- **Practice Projects**
		- 1
	
				def collatz(number):
					if number%2 = 0:
						return number//2
					else:
						return 3 * number + 1

	   	- 2
	
				 while True:
					num = input()
					ret = collatz(num)
					if ret == 1:
						break

					
				 

