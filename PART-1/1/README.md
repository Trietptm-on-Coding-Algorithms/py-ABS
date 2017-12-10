# Python Basics

 - `**` is an exponent operator
 - Operator Precedence is (From Left to right) - `**,%,//,/,*,-,+`
 - Small Brackets can be used to change the precedence to highest.
 - The * operator can be used with only two numeric values (for multiplication) or one string value and one integer value (for string replication). 
	 - `'Alice'*'Bob'` is not valid.
 - The `input()` function waits for the user to type some text on the keyboard and press enter. 
 - This is possible between `int` and `float`

			>>> 42 == '42' False 
			>>> 42 == 42.0 True 
			>>> 42.0 == 0042.000 True

 - **Practice Questions Solutions**
	 1. Which of the following are operators, and which are values? 
		- `* 'hello' -88.8 - / +` 
		- `* - / +`
	 2. Which of the following is a variable, and which is a string?
		- `spam 'spam'` 
		- `spam` is a variable, `'spam'` is a string because of quotes around it.
	 3. Name three data types.
		- `int, string, float, boolean , double`
	 4. What is an expression made up of? What do all expressions do?
		 - It is made up of operators and values(statements), expressions evaluates to a result.
	 5. This chapter introduced assignment statements, like spam = 10. What is the difference between an expression and a statement?
		- expressions always evaluates , statement may or may not.
	 6. What does the variable bacon contain after the following code runs?
		
			bacon = 20
			bacon + 1

		 - 21
	 7. What should the following two expressions evaluate to?

			'spam' + 'spamspam' 
			'spam' * 3

		 - `spamspamspamspamspamspamspamspamspam`
	
	 8. Why is eggs a valid variable name while 100 is invalid?
		- Variable name cannot start with numbers, it must be contain `strings, integer and underscore only`.
	 9. What three functions can be used to get the integer, floating-point number, or string version of a value?
	 	- `int(),float(),str()`
 	 10 Why does this expression cause an error? How can you fix it?  
		 `'I have eaten ' + 99 + ' burritos.'`
		 - Strings can't be concatenated with the integer.
		 - it should be - 
		 - `'I have eaten ' + str(99) + ' burritos.'`
