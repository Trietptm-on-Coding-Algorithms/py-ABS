# Flow Control

 - The three Boolean operators (and, or, and not) are used to compare Boolean values.
 - The `and` and `or` operators always take two Boolean values (or expressions), so they’re considered binary operators.
 - The `and` operator evaluates an expression to `True` if both Boolean values are `True`; otherwise, it evaluates to `False`.
 - There is no `else if` in python - use `elif`
 - When the program execution reaches a `continue` statement, the program execution immediately jumps back to the start of the loop and reevaluates the loop’s condition. 
 - you can even use a negative number for the step argument to make the for loop count down instead of up.
  - **Practice Questions**
	1. What are the two values of the Boolean data type? How do you write them?
		-`True` and `False`
	2. What are the three Boolean operators?
		- `and` , `or` , `not`
	3. Write out the truth tables of each Boolean operator (that is, every possible combination of Boolean values for the operator and what they evaluate to).
		- `and` 
		- `True` and `True`   - `True` 
		- `True` and `False`  - `False`
		- `False` and `True`  - `False`
		- `False` and `False` - `False`
		
		- `or` 
		- `True` and `True`   - `True` 
		- `True` and `False`  - `True`
		- `False` and `True`  - `True`
		- `False` and `False` - `False`
	4. What do the following expressions evaluate to?

				(5 > 4) and (3 == 5) - False
 				not (5 > 4) - False
 				(5 > 4) or (3 == 5) - True
				not ((5 > 4) or (3 == 5)) False
 				(True and True) and (True == False) - False
				(not False) or (not True)		 - True	
	5. What are the six comparison operators?
		- `==,<=,<,=>,>,!=`
	6. What is the difference between the equal to operator and the assignment operator? 
		- `=` assignment operator - assign the value to an variable
		- `==` equal to operator - compares the value b/w two.
	7. Explain what a condition is and where you would use one.
		- Where the is a need to make a decision.
	8.  
	9. 
	10. What can you press if your program is stuck in an infinite loop?
		- `Ctrl+c`

	11. What is the difference between break and continue?
		- `break` - Break the condition
		- `continue` - go back to start of loop
	12. What is the difference between range(10), range(0, 10), and range(0, 10, 1) in a for loop?
		 - `range(10)` - 0-9
		 - `range(0,10)` - 0-9
		 - `range(0,10,1)` - 0-9
	13. Write a short program that prints the numbers 1 to 10 using a for loop. Then write an equivalent program that prints the numbers 1 to 10 using a while loop.
				
				for i in range(0,10):
					print i
			
				i=0
				while(i<10):
					print i
					i=i+1

	14. If you had a function named bacon() inside a module named spam, how would you call it after importing spam?

		- Yes
		- import spam; spam.bacon()
		
