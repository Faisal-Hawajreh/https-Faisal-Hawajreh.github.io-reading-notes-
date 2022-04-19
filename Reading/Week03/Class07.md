# Modifying the Behavior of a Python Scope
So far, you’ve learned how a Python scope works and how they restrict the visibility of variables, functions, classes, and other Python objects to certain portions of your code. You now know that you can access or reference global names from any place in your code, but they can be modified or updated from within the global Python scope.

You also know that you can access local names only from inside the local Python scope they were created in or from inside a nested function, but you can’t access them from the global Python scope or from other local scopes. Additionally, you’ve learned that nonlocal names can be accessed from inside nested functions, but they can’t be modified or updated from there.

Even though Python scopes follow these general rules by default, there are ways to modify this standard behavior. Python provides two keywords that allow you to modify the content of global and nonlocal names. These two keywords are:

1. global
2. nonlocal
In the next two sections, you’ll cover how to use these Python keywords to modify the standard behavior of Python scopes.

## The global Statement
You already know that when you try to assign a value to a global name inside a function, you create a new local name in the function scope. To modify this behavior, you can use a global statement. With this statement, you can define a list of names that are going to be treated as global names.

The statement consists of the global keyword followed by one or more names separated by commas. You can also use multiple global statements with a name (or a list of names). All the names that you list in a global statement will be mapped to the global or module scope in which you define them.

Here’s an example where you try to update a global variable from within a function:

```
>>> counter = 0  # A global name
>>> def update_counter():
...     counter = counter + 1  # Fail trying to update counter
...
>>> update_counter()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 2, in update_counter
UnboundLocalError: local variable 'counter' referenced before assignment
```
  
  
When you try to assign counter inside update_counter(), Python assumes that counter is local to update_counter() and raises an UnboundLocalError because you’re trying to access a name that isn’t defined yet.

If you want this code to work the way you expect here, then you can use a global statement as follows:
```
>>> counter = 0  # A global name
>>> def update_counter():
...     global counter  # Declare counter as global
...     counter = counter + 1  # Successfully update the counter
...
>>> update_counter()
>>> counter
1
>>> update_counter()
>>> counter
2
>>> update_counter()
>>> counter
3
```
In this new version of update_counter(), you add the statement global counter to the body of the function right before you try to change counter. With this tiny change, you’re mapping the name counter in the function scope to the same name in the global or module scope. From this point on, you can freely modify counter inside update_counter(). All the changes will reflect in the global variable.

With the statement global counter, you’re telling Python to look in the global scope for the name counter. This way, the expression counter = counter + 1 doesn’t create a new name in the function scope, but updates it in the global scope.

## The nonlocal Statement
Similarly to global names, nonlocal names can be accessed from inner functions, but not assigned or updated. If you want to modify them, then you need to use a nonlocal statement. With a nonlocal statement, you can define a list of names that are going to be treated as nonlocal.

The nonlocal statement consists of the nonlocal keyword followed by one or more names separated by commas. These names will refer to the same names in the enclosing Python scope. The following example shows how you can use nonlocal to modify a variable defined in the enclosing or nonlocal scope:
```
>>> def func():
...     var = 100  # A nonlocal variable
...     def nested():
...         nonlocal var  # Declare var as nonlocal
...         var += 100
...
...     nested()
...     print(var)
...
>>> func()
200
```
With the statement nonlocal var, you tell Python that you’ll be modifying var inside nested(). Then, you increment var using an augmented assignment operation. This change is reflected in the nonlocal name var, which now has a value of 200.

Unlike global, you can’t use nonlocal outside of a nested or enclosed function. To be more precise, you can’t use a nonlocal statement in either the global scope or in a local scope. Here’s an example:
```
>>> nonlocal my_var  # Try to use nonlocal in the global scope
  File "<stdin>", line 1
SyntaxError: nonlocal declaration not allowed at module level
>>> def func():
...     nonlocal var  # Try to use nonlocal in a local scope
...     print(var)
...
  File "<stdin>", line 2
SyntaxError: no binding for nonlocal 'var' found
```
Here, you first try to use a nonlocal statement in the global Python scope. Since nonlocal only works inside an inner or nested function, you get a SyntaxError telling you that you can’t use nonlocal in a module scope. Notice that nonlocal doesn’t work inside a local scope either.

In contrast to global, you can’t use nonlocal to create lazy nonlocal names. Names must already exist in the enclosing Python scope if you want to use them as nonlocal names. This means that you can’t create nonlocal names by declaring them in a nonlocal statement in a nested function. Take a look at the following code example:
```
>>> def func():
...     def nested():
...         nonlocal lazy_var  # Try to create a nonlocal lazy name
...
  File "<stdin>", line 3
SyntaxError: no binding for nonlocal 'lazy_var' found
```
In this example, when you try to define a nonlocal name using nonlocal lazy_var, Python immediately raises a SyntaxError because lazy_var doesn’t exist in the enclosing scope of nested().

# Don't be CONFUSED by BIG O notation anymore!
[link](https://www.youtube.com/watch?v=5Uqawfl0VHQ&ab_channel=PythonProgrammer)

# Rolling Dice Examples

## Random
There is a package in Python that allows the use of random numbers.

### Program Example 1
Generate a random number from 1 to 6.

Easy peasy. We will just generate a random number from 1 to 6 with the package like this:
```
import random
print(random.randint(1,6))
```
As you can see, when you run this program, you get a random integer from 1 to 6.

### Program Example 2
Simulate the rolling of 1000 dice. Now, count the number of times you roll 6. Print that number out.

We can create a function that returns a random number from 1 to 6. Then, we can make a for loop that rolls the dice 1000 times and check if it is a 6.
```
import random
count = 0

def roll():
    return random.randint(1,6)

for i in range(1, 1001):
    if roll() == 6:
        count += 1

print(count)
```
If we run this, we will get a number around 170.

### Program Example 3
Simulate the rolling of 10,000 dice. Now, count the amount of times you roll 3. Print that amount out.

We can keep our roll function and our code inside the for loop, but we need to change our for loop statement.

We can actually soft-code our program more. Let's turn the whole for loop into a function!
```
import random

def roll():
    return random.randint(1,6)

def count(amount):
    count_ = 0

    for i in range(1, amount+1):
        if roll() == 3:
            count_ += 1
    return count_

print(count(10000))
```
If we run this code, it works.

### Program Example 4
One of my friends loves rolling dice. He is going to roll 1 die tomorrow, 2 dice two days from now, 3 dice three days from now, and so on so that he rolls $a$ dice $a$ days from now. He gets tired rolling dice after rolling dice for 365 days (so the last day he rolls 365 dice). In Python, simulate this. How many times does he roll 3 after 365 days of rolling dice?

We can use a for loop that calls a function multiple times.
```
import random

def roll():
    return random.randint(1,6)

def count(amount):
    count_ = 0
    for i in range(1, amount+1):
        if roll() == 3:
            count_ += 1
    return count_

total = 0

for i in range(1, 366):
    total += count(i)

print(total)
```
This is a really long program, but the whole program should make sense if you look at it for a while. We defined our count function in the previous example, and now we are using it with a for loop and a running total.

You should get a number around 11,000 when you run it. Wow, lots of 3's!

Program Example 5
20 of my friends love rolling dice. They are all going to roll 1 die each tomorrow, 2 dice each two days from now, 3 dice each three days from now, and so on so that they roll $a$ dice each $a$ days from now. But, one of my friends gets tired very quickly and he only rolls dice for 1 day and stops. Another friend only will roll dice for 2 days, and another will roll dice for three days only, and so on up to the fact that my last friend will roll dice for 20 days. In Python, simulate this. How many times does someone roll 3 after everything?

We will have to make our for loop into a function again.
```
import random

def roll():
    return random.randint(1,6)

def count(amount):
    count_ = 0
    for i in range(1, amount+1):
        if roll() == 3:
            count_ += 1
    return count_

def count2(amount):
    total = 0
    for i in range(1, amount + 1):
        total += count(i)
    return total

def count3(amount):
    total = 0
    for i in range(1, amount + 1):
        total += count2(i)
    return total

print(count3(20))
```
(Our program is so long!)

I also made a new function just in case we needed to turn that into a function later.

Make sure you read the code carefully and you fully understand it. If you don't understand every single line of code, then you will get confused later on in this article.

When you run this program, you might be surprised that the answer isn't so big.

### Program Example 6
365 of my friends love rolling dice. They are all going to roll 1 die each tomorrow, 2 dice each two days from now, 3 dice each three days from now, and so on so that they roll $a$ dice each $a$ days from now. But, one of my friends gets tired very quickly and he only rolls dice for 1 day and stops. Another friend only will roll dice for 2 days, and another will roll dice for three days only, and so on up to the fact that my last friend will roll dice for 365 days. In Python, simulate this. How many times does someone roll 3 after everything?

Because we soft-coded our program so much, all we have to do is change the last line so the parameter of count3() is 365.

If we run it...we get a big answer, as expected. It also takes quite a while!

You may not have realized that we soft-coded our program at all, but the whole point of functions is to soft-code programs!

Congrats on writing a program that is around 25 lines long!
