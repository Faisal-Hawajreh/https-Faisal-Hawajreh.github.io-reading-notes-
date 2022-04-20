# List Comprehensions
## Syntax
### Consider the following example:

my_new_list = [ expression for item in list ]

You can see from this example that three ingredients are necessary for a python list comprehension to work.

1. First is the expression we’d like to carry out. expression inside the square brackets.
2. Second is the object that the expression will work on. item inside the square brackets.
3. Finally, we need an iterable list of objects to build our new list from. list inside the square brackets.
To understand the list comprehension, imagine it like this: you’re going to perform an expression on each item in the list. The expression will determine what item is eventually stored in the output list. 

Not only can you perform expressions on an entire list in a single line of code, but, as we’ll see later, it’s possible to add conditional statements in the form of filters, which allows for more precision in the way lists are handled.

### Notes about Lists Comprehensions
- List comprehension methods are an elegant way to create and manage lists. 
- In Python, list comprehensions are a more compact way of creating lists. 
- More flexible than for loops, list comprehension is usually faster than other methods.

### Create a List with range()
Let’s start by creating a list of numbers using Python list comprehensions. We’ll take advantage of Python’s range() method as a way to create a list of digits.

#### Example 1: Creating a list with list comprehensions
```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)
```
Output
```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
````
Let’s break down this python example by starting with the first ‘x’. This is our expression. It doesn’t do anything because we’re simply recording the number. The second ‘x’ represents each item in the list created by the range() method.

In the python example above, we’re using the range() method to generate a list of numbers. Python iterates(or loops) through each item in that range, and saves a copy of the item in a new list called digits.

Perhaps that seems redundant? That’s only because you’ve yet to see the real potential of list comprehension.

### Create a List Using Loops and List Comprehension in Python
To better illustrate how a list comprehension can be used to write more efficient Python code, we’ll take a look at a side by side comparison. 

In the following example, you’ll see two different techniques for creating a Python list. The first is a for loop. We’ll use it to construct a list of the powers of two.

#### Example 2: Comparing list creation methods in Python

First, create a list and loop through it. Add an expression, in this example, we’ll raise x to the power of 2.
```
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
```
Output
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
The same thing can be done using a list comprehension, but with a fraction of the code. Let’s take a look at how to create a list of squares using the list comprehension method.
```
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
```
Even in this basic example, it’s obvious that list comprehensions reduce the code necessary to complete rather complicated task when working with a list.

### Multiplying Parts of a List
What if we wanted to multiply every number in a list by three in Python? We could write a for loop and store the results in a new list, or we could use list comprehensions.

#### Example 3: Multiplication with list comprehensions
```
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)
```
Output
```
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
```
By taking advantage of list comprehensions, it’s possible to work on only part of a list. For instance, if you only wanted the even numbers in a given range, you could find them using a filter.

Adding a filter to the list comprehension allows for greater flexibility. By using filters, we can select certain items from the list, while excluding others. This is an advanced feature of lists in Python.
```
even_numbers = [ x for x in range(1,20) if x % 2 == 0]
```
Output
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```
Show the first letter of each word using Python
So far we’ve seen examples of building a list of numbers in Python. Next, let’s try working with strings and the various ways list comprehensions can be used to elegantly handle a list of strings.

#### Example 4: Using list comprehensions with strings
```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
```
Output
```
['E', 'L', 'F', 'T', 'E', 'S']
```
List comprehensions can make solving issues involving strings much easier using simplified expressions. These methods can save time and precious lines of code.

#### Example 5: Separating the characters in a string
```
# use list comprehension to print the letters in a string
letters = [ letter for letter in "20,000 Leagues Under The Sea"]

print(letters)
```
Output
```
['2', '0', ',', '0', '0', '0', ' ', 'L', 'e', 'a', 'g', 'u', 'e', 's', ' ', 'U', 'n', 'd', 'e', 'r', ' ', 'T', 'h', 'e', ' ', 'S', 'e', 'a']
```
Lower/Upper case converter using Python
Using list comprehension to loop through a string in Python, it’s possible to convert strings from lower case to upper case, and vice versa. 

Making use of Python’s lower() and upper() methods, we’ll use list comprehension to achieve this common task.

#### Example 6: Changing a letter’s case
```
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
```
Output
```
['a', 'b', 'c'] ['A', 'B', 'C']
```
Print numbers only from a given string
Another interesting exercise is to extract numbers from a string. For example, we may have a database of names and phone numbers.

It would be useful if we could separate the phone numbers from the names. Using list comprehensions, we can do just that.

Taking advantage of Python’s isdigit() method, we can extract the phone number from the user data.

#### Example 7: Identify numbers in a string using the isdigit() method
```
# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
```
Output
```
['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```
### Parsing a file using list comprehension
It’s also possible to read files in Python using list comprehension. To demonstrate, I’ve created a file called dreams.txt and pasted the following text, a short poem by Langston Hughes.

Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

Langston Hughes


Using list comprehension, we can iterate through the lines of text in the file and store their contents in a new list.

#### Example 8: Reading a poem with list comprehensions
```
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
```
Output
```
Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
```
### Using functions in list comprehensions
So far we’ve seen how to use list comprehension to generate lists using some basic Python methods like lower() and upper(). But what if we wanted to use our own Python functions?

Not only can we write our own functions with list comprehensions, but we can also add filters to better control the statements.

#### Example 9: Adding arguments to list comprehension
```
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
```
Output
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```
Filtering elements from the list can be done using additional arguments. In the following example, only even numbers are selected.
```
# add a filter so we only double even numbers
even_nums = [double(x) for x in range(1,10) if x%2 == 0]
print(even_nums)
```
Output
```
[4, 8, 12, 16]
```
Additional arguments can be added to create more complex logic:
```
nums = [x+y for x in [1,2,3] for y in [10,20,30]]
print(nums)
```
Output
```
[11, 21, 31, 12, 22, 32, 13, 23, 33]
```

# Simple Decorators
Now that you’ve seen that functions are just like any other object in Python, you’re ready to move on and see the magical beast that is the Python decorator. Let’s start with an example:
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

def say_whee():
    print("Whee!")

say_whee = my_decorator(say_whee)
```
Can you guess what happens when you call say_whee()? Try it:
```
>>> say_whee()
Something is happening before the function is called.
Whee!
Something is happening after the function is called.
```
To understand what’s going on here, look back at the previous examples. We are literally just applying everything you have learned so far.

The so-called decoration happens at the following line:
```
say_whee = my_decorator(say_whee)
```
In effect, the name say_whee now points to the wrapper() inner function. Remember that you return wrapper as a function when you call my_decorator(say_whee):
```
>>> say_whee
<function my_decorator.<locals>.wrapper at 0x7f3c5dfd42f0>
```
However, wrapper() has a reference to the original say_whee() as func, and calls that function between the two calls to print().

Put simply: decorators wrap a function, modifying its behavior.

Before moving on, let’s have a look at a second example. Because wrapper() is a regular Python function, the way a decorator modifies a function can change dynamically. So as not to disturb your neighbors, the following example will only run the decorated code during the day:
```
from datetime import datetime

def not_during_the_night(func):
    def wrapper():
        if 7 <= datetime.now().hour < 22:
            func()
        else:
            pass  # Hush, the neighbors are asleep
    return wrapper

def say_whee():
    print("Whee!")

say_whee = not_during_the_night(say_whee)
```
If you try to call say_whee() after bedtime, nothing will happen:
```
>>> say_whee()
>>>
```
## Syntactic Sugar!
The way you decorated say_whee() above is a little clunky. First of all, you end up typing the name say_whee three times. In addition, the decoration gets a bit hidden away below the definition of the function.

Instead, Python allows you to use decorators in a simpler way with the @ symbol, sometimes called the “pie” syntax. The following example does the exact same thing as the first decorator example:
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```
So, @my_decorator is just an easier way of saying say_whee = my_decorator(say_whee). It’s how you apply a decorator to a function.

## Reusing Decorators
Recall that a decorator is just a regular Python function. All the usual tools for easy reusability are available. Let’s move the decorator to its own module that can be used in many other functions.

Create a file called decorators.py with the following content:
```
def do_twice(func):
    def wrapper_do_twice():
        func()
        func()
    return wrapper_do_twice
```
> Note: You can name your inner function whatever you want, and a generic name like wrapper() is usually okay. You’ll see a lot of decorators in this article. To keep them apart, we’ll name the inner function with the same name as the decorator but with a wrapper_ prefix.

You can now use this new decorator in other files by doing a regular import:
```
from decorators import do_twice

@do_twice
def say_whee():
    print("Whee!")
```
When you run this example, you should see that the original say_whee() is executed twice:
```
>>> say_whee()
Whee!
Whee!
```

## Decorating Functions With Arguments
Say that you have a function that accepts some arguments. Can you still decorate it? Let’s try:
```
from decorators import do_twice

@do_twice
def greet(name):
    print(f"Hello {name}")
```
Unfortunately, running this code raises an error:
```
>>> greet("World")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: wrapper_do_twice() takes 0 positional arguments but 1 was given
```
The problem is that the inner function wrapper_do_twice() does not take any arguments, but name="World" was passed to it. You could fix this by letting wrapper_do_twice() accept one argument, but then it would not work for the say_whee() function you created earlier.

The solution is to use *args and **kwargs in the inner wrapper function. Then it will accept an arbitrary number of positional and keyword arguments. Rewrite decorators.py as follows:
```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        func(*args, **kwargs)
    return wrapper_do_twice
```
The wrapper_do_twice() inner function now accepts any number of arguments and passes them on to the function it decorates. Now both your say_whee() and greet() examples works:
```
>>> say_whee()
Whee!
Whee!

>>> greet("World")
Hello World
Hello World
```

## Returning Values From Decorated Functions
What happens to the return value of decorated functions? Well, that’s up to the decorator to decide. Let’s say you decorate a simple function as follows:
```
from decorators import do_twice

@do_twice
def return_greeting(name):
    print("Creating greeting")
    return f"Hi {name}"
```
Try to use it:
```
>>> hi_adam = return_greeting("Adam")
Creating greeting
Creating greeting
>>> print(hi_adam)
None
```
Oops, your decorator ate the return value from the function.

Because the do_twice_wrapper() doesn’t explicitly return a value, the call return_greeting("Adam") ended up returning None.

To fix this, you need to make sure the wrapper function returns the return value of the decorated function. Change your decorators.py file:
```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs)
    return wrapper_do_twice
```
The return value from the last execution of the function is returned:
```
>>> return_greeting("Adam")
Creating greeting
Creating greeting
'Hi Adam'
```
## Who Are You, Really?
A great convenience when working with Python, especially in the interactive shell, is its powerful introspection ability. Introspection is the ability of an object to know about its own attributes at runtime. For instance, a function knows its own name and documentation:
```
>>> print
<built-in function print>

>>> print.__name__
'print'

>>> help(print)
Help on built-in function print in module builtins:

print(...)
    <full help message>
```
The introspection works for functions you define yourself as well:
```
>>> say_whee
<function do_twice.<locals>.wrapper_do_twice at 0x7f43700e52f0>

>>> say_whee.__name__
'wrapper_do_twice'

>>> help(say_whee)
Help on function wrapper_do_twice in module decorators:

wrapper_do_twice()
```
However, after being decorated, say_whee() has gotten very confused about its identity. It now reports being the wrapper_do_twice() inner function inside the do_twice() decorator. Although technically true, this is not very useful information.

To fix this, decorators should use the @functools.wraps decorator, which will preserve information about the original function. Update decorators.py again:
```
import functools

def do_twice(func):
    @functools.wraps(func)
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs)
    return wrapper_do_twice
```
You do not need to change anything about the decorated say_whee() function:
```
>>> say_whee
<function say_whee at 0x7ff79a60f2f0>

>>> say_whee.__name__
'say_whee'

>>> help(say_whee)

Help on function say_whee in module whee:

say_whee()
```
Much better! Now say_whee() is still itself after decoration.

Technical Detail: The @functools.wraps decorator uses the function functools.update_wrapper() to update special attributes like __name__ and __doc__ that are used in the introspection.

