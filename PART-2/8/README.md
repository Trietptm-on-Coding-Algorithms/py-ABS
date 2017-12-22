# Reading and Writing Files.
- Variables are a fine way to store data while your program is running, but if you want your data to persist even after your program has finished, you need to save it to a file.
- On Windows, paths are written using backslashes (\) as the separator between folder names. OS X and Linux, however, use the forward slash (/) as their path separator. If you want your programs to work on all operating systems, you will have to write your Python scripts to handle both cases. 
- The `os.path.join()` function is helpful if you need to create strings for filenames. 
- You can get the current working directory as a string value with the `os.getcwd()` function and change it with `os.chdir()`.
- There are two ways to specify a file path.
	- • An absolute path, which always begins with the root folder 
	- • A relative path, which is relative to the program’s current working directory 
- Your programs can create new folders (directories) with the `os.makedirs()` function. 
- **os.path module**
	- `os.path.abspath('.')` - Calling os.path.abspath(path) will return a string of the absolute path of the argument. This is an easy way to convert a relative path into an absolute one.
	- Calling `os.path.isabs(path)` will return `True` if the argument is an absolute path and `False` if it is a relative path.
	- Calling `os.path.dirname(path)` will return a string of everything that comes before the last slash in the path argument. 
	- Calling `os.path.basename(path)` will return a string of everything that comes after the last slash in the path argument.
	- If you need a path’s dir name and base name together, you can just call `os.path.split()` to get a tuple value with these two strings.
- **Finding File Sizes and Folder Contents**
	- Calling `os.path.getsize(path)` will return the size in bytes of the file in the path argument.
	- Calling `os.listdir(path)` will return a list of filename strings for each file in the path argument.
- **Checking Path Validity**
	- Calling `os.path.exists(path)` will return `True` if the file or folder referred to in the argument exists and will return `False` if it does not exist.
	- Calling `os.path.isfile(path)` will return `True` if the path argument exists and is a file and will return `False` otherwise.
	- Calling `os.path.isdir(path)` will return `True` if the path argument exists and is a folder and will return `False` otherwise.
- **The File Reading/Writing Process**
	- There are three steps to reading or writing files in Python.
		 1. Call the `open()` function to return a File object. 
		 2. Call the `read()` or `write()` method on the File object. 
		 3. Close the file by calling the `close()` method on the File object.

	- To open a file with the `open()` function, you pass it a string path indicating the file you want to open; it can be either an absolute or relative path. The `open()` function returns a File object.

	- **Reading the Contents of Files**
		- If you want to read the entire contents of a file as a string value, use the File object’s `read()` method.
		- you can use the `readlines()` method to get a list of string values from the file, one string for each line of text.
	- **Writing to Files**
		- Write mode will overwrite the existing file and start from scratch, just like when you overwrite a variable’s value with a new value.
		- Pass 'w' as the second argument to `open()` to open the file in write mode.
		- Append mode, on the other hand, will append text to the end of the existing file. You can think of this as appending to a list in a variable, rather than overwriting the variable altogether.
		- Pass 'a' as the second argument to `open()` to open the file in append mode.
		- If the filename passed to open() does not exist, both write and append mode will create a new, blank file. After reading or writing a file, call the close() method before opening the file again.
		- the `write()` method does not automatically add a newline character to the end of the string like the print() function does. You will have to add this character yourself. 
	
	- **Saving Variables with the shelve Module**
		- You can save variables in your Python programs to binary shelf files using the shelve module. This way, your program can restore data to variables from the hard drive. The shelve module will let you add Save and Open features to your program. For example, if you ran a program and entered some configuration settings, you could save those settings to a shelf file and then have the program load them the next time it is run.
		- Your programs can use the shelve module to later reopen and retrieve the data from these shelf files. Shelf values don’t have to be opened in read or write mode—they can do both once opened. 
	- **Saving Variables with the pprint.pformat() Function**
		- The `pprint.pformat()` function will return this same text as a string instead of printing it. Not only is this string formatted to be easy to read, but it is also syntactically correct Python code. 
		- Using `pprint.pformat()` will give you a string that you can write to .py file. This file will be your very own module that you can import whenever you want to use the variable stored in it.
		- The benefit of creating a `.py` file (as opposed to saving variables with the shelve module) is that because it is a text file, the contents of the file can be read and modified by anyone with a simple text editor. 
 
**Project: Generating Random Quiz Files**

 



	import random

				capitals =   {'Alabama': 'Montgomery', 'Alaska': 'Juneau', 'Arizona': 'Phoenix','Arkansas': 'Little Rock', 'California': 'Sacramento', 'Colorado': 'Denver','Connecticut': 'Hartford', 'Delaware': 'Dover', 'Florida': 'Tallahassee','Georgia': 'Atlanta', 'Hawaii': 'Honolulu', 'Idaho': 'Boise', 'Illinois':'Springfield', 'Indiana': 'Indianapolis', 'Iowa': 'Des Moines', 'Kansas':'Topeka', 'Kentucky': 'Frankfort', 'Louisiana': 'Baton Rouge', 'Maine':'Augusta', 'Maryland': 'Annapolis', 'Massachusetts': 'Boston', 'Michigan':'Lansing', 'Minnesota': 'Saint Paul', 'Mississippi': 'Jackson', 'Missouri':'Jefferson City', 'Montana': 'Helena', 'Nebraska': 'Lincoln', 'Nevada':'Carson City', 'New Hampshire': 'Concord', 'New Jersey': 'Trenton', 'New Mexico': 'Santa Fe', 'New York': 'Albany','North Carolina': 'Raleigh','North Dakota': 'Bismarck', 'Ohio': 'Columbus', 'Oklahoma': 'Oklahoma City','Oregon': 'Salem', 'Pennsylvania': 'Harrisburg', 'Rhode Island': 'Providence','South Carolina': 'Columbia', 'South Dakota': 'Pierre', 'Tennessee':'Nashville', 'Texas': 'Austin', 'Utah': 'Salt Lake City', 'Vermont':'Montpelier', 'Virginia': 'Richmond', 'Washington': 'Olympia', 'West Virginia': 'Charleston', 'Wisconsin': 'Madison', 'Wyoming': 'Cheyenne'}


	for quiznum in range(35):
		quizFile = open('capitalquiz%s.txt' % (quiznum+1),'w')
		answerkeyFile = open('capita;quizans%s.txt' %(quiznum+1), 'w')

	quizFile.write('Name:\n\nDate:\n\nPeriod:\n\n')
	quizFile.write((' '*20) + 'State Capital Quiz (Form%s)' % (quiznum+1))
	quizFile.write('\n\n')


	states = list(capitals.keys())
	random.shuffle(states)

	for questionNum in range(50):
		correctAnswer  = capitals[states[questionNum]]
		wrongAns = list(capitals.values())
		del wrongAns[wrongAns.index(correctAnswer)]
		wrongAns = random.sample(wrongAns,3)
		answerOptions = wrongAns + [correctAnswer]
		random.shuffle(answerOptions)



		quizFile.write('%s. What is the capital of %s?' %(questionNum +1,states[questionNum]))
		for i in range(4):
			quizFile.write('  %s.%s?\n' % ('ABCD'[i], answerOptions[i]))
		quizFile.write('\n')


		answerkeyFile.write('%s . %s\n' %(questionNum +1, 'ABCD'[answerOptions.index(correctAnswer)]))

	quizFile.close()
	answerkeyFile.close()


**Project: Multiclipboard**

 - The `.pyw` extension means that Python won’t show a Terminal window when it runs this program.

		import sys, pyperclip,shelve

		mcbShelf = shelve.open('mcb')

		if len(sys.argv) == 3 and sys.argv[1].lower == 'save':
    		mcbShelf[sys.argv[2]] = pyperclip.paste()


		elif len(sys.argv) == 2:
    		if sys.argv[1].lower() == 'list':
        		pyperclip.copy(str(list(mcbShelf.keys())))
    		elif sys.argv[1] in mcbShelf:
        		pyperclip.copy(mcbShelf[sys.argv[1]])

		mcbShelf.close()


**Practice Quesrions**

  1. What is a relative path relative to?
		- Check the destination relative to current location.

  2. What does an absolute path start with?
		- `/`
	
  3. What do the os.getcwd() and os.chdir() functions do?
		- get the current working directory and change the working directory to other location 

	4. What are the . and .. folders?
		- `.` Current location and `..` one step back folder location 
 
	5. In C:\bacon\eggs\spam.txt, which part is the dir name, and which part is the base name?
		- `C:\bacon\eggs\` - Dir , base - `spam.txt`
	
	6. What are the three “mode” arguments that can be passed to the open() function?
		- Read , Write and Append.
	
	7. What happens if an existing file is opened in write mode?
		- It gets overwritten.
 
	8. What is the difference between the read() and readlines() methods?
		- read - `read the line till line break(\n) and store it in a variable`
		- readlines - `read the multiple lines till line break(\n) and store it in list`		
	9. What data structure does a shelf value resemble?
 		- `Instance`
