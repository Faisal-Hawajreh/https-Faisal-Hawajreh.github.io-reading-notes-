## Files on most modern file systems are composed of three main parts:

Header: metadata about the contents of the file (file name, size, type, and so on)
Data: contents of the file as written by the creator or editor.
End of file (EOF): a special character that indicates the end of the file.


## File Paths

When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows).
File Name: the actual name of the file.
Extension: the end of the file path pre-pended with a period (.) used to indicate the file type.

- You can use the special characters double-dot (..) to move one directory up




## Character Encodings

An encoding is a translation from byte data to human-readable characters. This is typically done by assigning a numerical value to represent a character. The two most common encodings are the ASCII and UNICODE Formats.

Opening and Closing a File in Python

It’s important to remember that it’s your responsibility to close the file. In most cases, upon the termination of an application or script, a file will be closed eventually. However, there is no guarantee when exactly that will happen. This can lead to unwanted behavior including resource leaks. It’s also a best practice within Python (Pythonic) to make sure that your code behaves in a way that is well defined and reduces any unwanted behavior.

When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:

reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()



The second way to close a file is to use the with statement:

with open('dog_breeds.txt') as reader: # Further file processing goes here

The with statement automatically takes care of closing the file once it leaves the with block, even in cases of error. I highly recommend that you use the with statement as much as possible, as it allows for cleaner code and makes handling any unexpected errors easier for you.

Most likely, you’ll also want to use the second positional argument, mode. This argument is a string that contains multiple characters to represent how you want to open the file. The default and most common is 'r', which represents opening the file in read-only mode as a text file:

with open('dog_breeds.txt', 'r') as reader:
    # Further file processing goes here

Other options for modes are fully documented online, but the most commonly used ones are the following:
Character	Meaning
'r'	Open for reading (default)
'w'	Open for writing, truncating (overwriting) the file first
'rb' or 'wb'	Open in binary mode (read/write using byte data)


There are three different categories of file objects:

Text files
Buffered binary files
Raw binary files

## Reading and Writing Opened Files

There are multiple methods that can be called on a file object to help you out:

## Method	What It Does
.read(size=-1) :	This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.
.readline(size=-1)	:This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.
.readlines()	:This reads the remaining lines from the file object and returns them as a list.

Don’t Re-Invent the Snake

There are common situations that you may encounter while working with files. Most of these cases can be handled using other modules. Two common file types you may need to work with are .csv and .json. Real Python has already put together some great articles on how to handle these:

Reading and Writing CSV Files in Python
Working With JSON Data in Python

Additionally, there are built-in libraries out there that you can use to help you:

wave: read and write WAV files (audio)
aifc: read and write AIFF and AIFC files (audio)
sunau: read and write Sun AU files
tarfile: read and write tar archive files
zipfile: work with ZIP archives
configparser: easily create and parse configuration files
xml.etree.ElementTree: create or read XML based files
msilib: read and write Microsoft Installer files
plistlib: generate and parse Mac OS X .plist files

There are plenty more out there. Additionally there are even more third party tools available on PyPI. Some popular ones are the following:

PyPDF2: PDF toolkit
xlwings: read and write Excel files
Pillow: image reading and manipulation
Exceptions versus Syntax Errors

Syntax errors occur when the parser detects an incorrect statement. Observe the following example:

   print( 0 / 0 ))
   File "<stdin>", line 1
      print( 0 / 0 ))
                    ^
SyntaxError: invalid syntax

The arrow indicates where the parser ran into the syntax error


   print( 0 / 0)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ZeroDivisionError: integer division or modulo by zero

This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.


## Raising an Exception

We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

  x = 10
  if x > 5:
      raise Exception('x should not exceed 5. The value of x was: {}'.format(x))


When you run this code, the output will be the following:

Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10

## The AssertionError Exception

We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.



## Exception FileNotFoundError

Raised when a file or directory is requested but doesn’t exist. Corresponds to errno ENOENT.

## Summing Up

After seeing the difference between syntax errors and exceptions, you learned about various ways to raise, catch, and handle exceptions in Python. In this article, you saw the following options:

raise allows you to throw an exception at any time.
assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
In the try clause, all statements are executed until an exception is encountered.
except is used to catch and handle the exception(s) that are encountered in the try clause.
else lets you code sections that should run only when no exceptions are encountered in the try clause.
finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.





