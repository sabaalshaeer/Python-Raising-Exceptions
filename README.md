# Python-Raising-Exceptions
Create a custom exception module.

In the wordprocess.py tab, scroll as needed to view the read_input_file method, which starts at line 50.

You have already added an exception handler to deal with FileNotFoundError exceptions.

In the Project pane, right-click WordCount and select New→Python File.


In the New Python file dialog box, in the Name text box, type wordexceptions and press Enter.


Verify that wordexceptions.py has opened in the editing area.

Create two custom exception classes.

Enter the code as shown.


Two custom exception classes are defined in this script.

Line 4 creates the class FileEmptyError by inheriting from Python's general Exception class.
A class is not allowed to be empty, so line 9 uses a pass statement as a placeholder. The pass statement will do nothing when executed.
This approach enables you to define a barebones custom exception.
A slightly more complex custom exception is defined starting in line 12.

Line 12 creates the class FileTooBigError by inheriting from Python's general Exception class.
Lines 18-20 construct an instance of the custom exception class, taking in a file size argument that is assigned to the class's size attribute when the exception is raised. In the exception handler, this value can be read to determine the size of the file that was too large.
Lines 22-24 implement a method that returns the size attribute as a value of type float.
Import the new custom exception.

Select the wordprocess.py tab.

To the left of the import statement in line 5, select the + button to show all of the import statements.

Position the insertion point at the end of line 8, and press Enter.

Type from wordexceptions import FileEmptyError, FileTooBigError

This imports both exception classes from the wordexceptions.py file.

Raise the new custom exceptions in your code.

Position the insertion point at the end of line 60.

Press Enter.

Enter the code shown here.

4hw6rm9p.jpg

If the size of the user's input file (self.file) exceeds 10 megabytes, then the FileTooBig exception will be raised, constructing an instance of the class and passing in the file size in megabytes. The argument passed into this class instance is the user's file size formatted into MBs.
If the size of the file is zero bytes (empty file), then the FileEmptyError exception will be raised.
If you were planning to handle the exception outside of the class (in wordcount.py, for example), you would be done working in wordprocess.py at this point. The exceptions will be raised, and if not handled within this class or in outside code that uses the class, then the exceptions will be reported by the Python interpreter.
Test your custom exception with bad input files.

Run wordcount.py.

For the input file, enter large_file.txt

Verify that Python encountered your custom exception and reported the exception.


The exception is unhandled, so the program exits with a code 1.

Run wordcount.py again.

For the input file, enter empty.txt.

Again, the exception is unhandled, so the program exits with a code 1.

Write code to handle the custom exceptions.

Position the insertion point at the end of line 76.

Press Enter twice.

Type the code shown here.


If one of these exceptions occurs, then a message will be shown to the user and read_input_file will return False.
In the FileTooBigError exception handler, the message will display the size of the file that was too large.
Test your custom exception handler with a large input file.

Run wordcount.py.
For the input file, enter large_file.txt
Verify that Python encountered your custom exception and printed the warning you defined in your exception handling code.
