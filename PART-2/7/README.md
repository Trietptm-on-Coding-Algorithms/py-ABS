# Pattern Matching with Regular Expressions
- Regular expressions, called regexes for short, are descriptions for a pattern of text. 
- `import re` imports regex in python program

		>>> phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
		>>> mo = phoneNumRegex.search('My number is 415-555-4242.')
		>>> print('Phone number found: ' + mo.group()) Phone number found: 415-555-4242
		>>> 415-555-4242

- Passing a string value representing your regular expression to `re.compile()` returns a Regex pattern object.
- Passing Raw Strings to `re.compile()` , - use `r''` it eliminates the headache of using escape characters.
- A Regex object’s `search()` method searches the string it is passed for any matches to the regex, if `False` it returns `None`
- Review of Regex Expression Matching
	1. Import the regex module with `import re`.
	2. Create a Regex object with the `re.compile()` function. (Remember to use a raw string.) 
	3. Pass the string you want to search into the Regex object’s `search()` method. This returns a Match object.
	4. Call the Match object’s `group()` method to return a string of the actual matched text.

 - Adding parentheses will create groups in the regex: `(\d\d\d)-(\d\d\d-\d\d\d\d)`
 - The first set of parentheses in a regex string will be group 1. The second set will be group 2. By passing the integer 1 or 2 to the group() match object method, you can grab different parts of the matched text. Passing 0 or nothing to the `group(`) method will return the entire matched text.
 - If you would like to retrieve all the groups at once, use the `groups()`
	 - `a,b = res.groups()`
 - To Escape parenthesis use `\( and \)`
 - The `|` character is called a pipe. You can use it anywhere you want to match one of many expressions. 
 - You can use it anywhere you want to match one of many expressions. For example, the regular expression `r'Batman|Tina Fey'` will match either `'Batman'` or `'Tina Fey'`. When both Batman and Tina Fey occur in the searched string, the first occurrence of matching text will be returned as the Match object. 
	 - `>>> batRegex = re.compile(r'Bat(man|mobile|copter|bat)')`

 - Optional Matching with the Question Mark
	 - The `?` character flags the group that precedes it as an optional part of the pattern. 
		`batRegex = re.compile(r'Bat(wo)?man')`
 - Matching Zero or More with the Star
	 - `batRegex = re.compile(r'Bat(wo)*man')`
	 - `mo3 = batRegex.search('The Adventures of Batwowowowoman')`

 - Matching One or More with the Plus
	- While `*` means “match zero or more,” the `+` (or plus) means “match one or more.” Unlike the star, which does not require its group to appear in the matched string, the group preceding a plus must appear at least once. It is not optional.
 
 - Matching Specific Repetitions with Curly Brackets
	- If you have a group that you want to repeat a specific number of times, follow the group in your regex with a number in curly brackets. For example, the regex `(Ha){3}` will match the string `'HaHaHa'`, but it will not match `'HaHa'`, since the latter has only two repeats of the (Ha) group
	- Instead of one number, you can specify a range by writing a minimum, a comma, and a maximum in between the curly brackets. For example, the regex `(Ha){3,5}` will match `'HaHaHa', 'HaHaHaHa', and 'HaHaHaHaHa'`.
 
 - Greedy and Nongreedy Matching
	- Python’s regular expressions are greedy by default, which means that in ambiguous situations they will match the longest string possible. The nongreedy version of the curly brackets, which matches the shortest string possible, has the closing curly bracket followed by a question mark.
 - The `findall()` Method
	 - In addition to the `search()` method, Regex objects also have a `findall()` method. While `search()` will return a Match object of the first matched text in the searched string, the `findall()` method will return the strings of every match in the searched string.
 - `\d` is shorthand for the regular expression `(0|1|2|3|4|5|6|7|8|9)`.
	 - \d Any numeric digit from 0 to 9.
	 - \D Any character that is not a numeric digit from 0 to 9. 
	 - \w Any letter, numeric digit, or the underscore character. (Think of this as matching “word” characters.) 
	 - \W Any character that is not a letter, numeric digit, or the underscore character. 
	 - \s Any space, tab, or newline character. (Think of this as matching “space” characters.) 
	 - \S Any character that is not a space, tab, or newline.

 - You can define your own character class using square brackets. ex: `[aeiouAEIOU]`
 - You can also include ranges of letters or numbers by using a hyphen.  ex `s [a-zA-Z0-9]`
	- you do not need to escape the `., *, ?, or ()` characters with a preceding backslash inside square brackets.
 - By placing a caret character (`^`) just after the character class’s opening bracket, you can make a negative character class. A negative character class will match all the characters that are not in the character class.  
 - The Caret and Dollar Sign Characters
	- You can also use the caret symbol (`^`) at the start of a regex to indicate that a match must occur at the beginning of the searched text. Likewise, you can put a dollar sign (`$`) at the end of the regex to indicate the string must end with this regex pattern.
	- you can use the `^` and `$` together to indicate that the entire string must match the regex—that is, it’s not enough for a match to be made on some subset of the string. 
	
- The Wildcard Character
	- The `.` (or dot) character in a regular expression is called a wildcard and will match any character except for a newline.
	- Matching Everything with Dot-Star
		- Sometimes you will want to match everything and anything. For example, say you want to match the string 'First Name:', followed by any and all text, followed by 'Last Name:', and then followed by anything again. You can use the dot-star (.*) to stand in for that “anything.” Remember that the dot character means “any single character except the newline,” and the star character means “zero or more of the preceding character.”
		- The dot-star uses greedy mode: It will always try to match as much text as possible. To match any and all text in a nongreedy fashion, use the dot, star, and question mark (.*?).
	- Matching Newlines with the Dot Character
		- The dot-star will match everything except a newline. By passing re.DOTALL as the second argument to re.compile(), you can make the dot character match all characters, including the newline character.
 
**Review**

			• The ? matches zero or one of the preceding group. 
			• The * matches zero or more of the preceding group. 
			• The + matches one or more of the preceding group. 
			• The {n} matches exactly n of the preceding group. 
			• The {n,} matches n or more of the preceding group. 
			• The {,m} matches 0 to m of the preceding group. 
			• The {n,m} matches at least n and at most m of the preceding group. 
			• {n,m}? or *? or +? performs a nongreedy match of the preceding group. 
			• ^spam means the string must begin with spam. 
			• spam$ means the string must end with spam. 
			• The . matches any character, except newline characters. 
			• \d, \w, and \s match a digit, word, or space character, respectively. 
			• \D, \W, and \S match anything except a digit, word, or space character, respectively. 
			• [abc] matches any character between the brackets (such as a, b, or c). 
			• [^abc] matches any character that isn’t between the brackets.

 - Case-Insensitive Matching
	- To make your regex case-insensitive, you can pass re.IGNORECASE or re.I as a second argument to re.compile().
 
 - Substituting Strings with the sub() Method
	- Regular expressions can not only find text patterns but can also substitute new text in place of those patterns. The `sub()` method for Regex objects is passed two arguments. The first argument is a string to replace any matches. The second is the string for the regular expression. The sub() method returns a string with the substitutions applied.
		- `namesRegex = re.compile(r'Agent \w+')`
		- `namesRegex.sub('CENSORED', 'Agent Alice gave the secret documents to Agent Bob.')`

 - `#` can be use to comment.

### Project: Phone Number and Email Address Extractor

 

	import re, pyperclip

	phoneReg = re.compile(r'(\d{3}|\(\d{3}\))?(\s|-|\.)?(\d{3})(\s|-|\.)(\d{4})(\s*(ext|ext.|ex)\s*(\d{2-4}))?',re.VERBOSE)

	emailReg = re.compile(r'([a-zA-Z0-9._]+)(@)([a-zA-Z0-9]+)(\.[a-zA-Z]{2,4})')

	text =str(pyperclip.paste())

	matches = []

	for groups in phoneReg.findall(text):

	   	phoneNum = '-'.join([groups[0], groups[2],groups[4]])
    	matches.append(phoneNum)

	for groups in emailReg.findall(text):
   	 matches.append(groups[0]+groups[1]+groups[2]+groups[03])

	if len(matches)>0:
		   	pyperclip.copy('\n'.join(matches))
			print('Copied to clipboard:')
  			print('\n'.join(matches))


	else:
		print('No phone or emails found.')

 - **Practice Questions**
	1. What is the function that creates Regex objects?
		- `re.compile()`
	2. Why are raw strings often used when creating Regex objects?
		- So we can easily work with escape characters.
	3. What does the search() method return?
		- Searches and return the first occurrence of object.
	4. How do you get the actual strings that match the pattern from a Match object?
		- Using groups
	5. In the regex created from r'(\d\d\d)-(\d\d\d-\d\d\d\d)', what does group 0 cover? Group 1? Group 2?
		- group 0 All
		- group 1 First 
		- group 2 Second
	6. Parentheses and periods have specific meanings in regular expression syntax. How would you specify that you want a regex to match actual parentheses and period characters?
		- Using escape sequences
			- `\(\)`
			- `\.`
	7. The findall() method returns a list of strings or a list of tuples of strings. What makes it return one or the other? 
		- Parenthesis in object.
	8. What does the | character signify in regular expressions?
		- TO match one of more conditions
	9. What two things does the ? character signify in regular expressions?
		- Optional if is outside the parenthesis
		- matches zero or one of the preceding group.
	10. What is the difference between the + and * characters in regular expressions?
		- `+` zero or more occurrences
		- `*` one or more occurrences
	11. What is the difference between {3} and {3,5} in regular expressions?
		- {3} characters
		- {3,5} three to five characters.
	12. What do the \d, \w, and \s shorthand character classes signify in regular expressions?
		- digit, word, space
	13. What do the \D, \W, and \S shorthand character classes signify in regular expressions?
		- Not digit, not word, not space.
	14. How do you make a regular expression case-insensitive?
		- By using re.IGNORECASE()
	15. What does the . character normally match? What does it match if re.DOTALL is passed as the second argument to re.compile()?
		- matches All but not new line,  if re.DOTALL is passed it also matches with new line.
	16. What is the difference between .* and .*?
		- `.*` - zero or one occurrences of `.`
		- non-greedy mode.

	17. What is the character class syntax to match all numbers and lowercase letters?
		- [0-9a-z]
	18. If numRegex = re.compile(r'\d+'), what will numRegex.sub('X', '12 drummers, 11 pipers, five rings, 3 hens') return?
		- `X drummers, X pipers, five rings, X hens`

	19. What does passing re.VERBOSE as the second argument to re.compile() allow you to do?
		- You can add comments.
	20. How would you write a regex that matches a number with commas for every three digits? It must match the following:
		- See book
			- 
