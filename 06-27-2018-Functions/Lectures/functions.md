# Functions

## General Advice
If you are repeating yourself, you are likely doing it wrong.

## Functions
We've already been working with them but we can create our own!

```python
tweet = 'My Professor @JessicaGarson is so awesome'
len(tweet)
tweet_length = len(tweet)
print(tweet)
print('Your tweet is {}, and it contains {} charcters'.format(tweet, tweet_length))
video_game = input("What's your favorite video game?\n")
print('{} is a great video game, I got to go now see you later!'.format(video_game))
```

## So What Are Functions
They are like a mini program inside of your program that contain reusable code. They are only run when they are called and they prevent errors and bugs in our code by avoiding duplication.

## Let's Write a Function
We can create a function for our hello world program:

```python
def hello_world():
    print('Hello World!')


hello_world()
```

All functions have what's know as a def statement that allows us to define our function. And inside of the body of our code we can write our code in it.

```python
def hello(name):
    print('Hello {}'.format(name))


# first way
hello('Zack')
hello('Amy')

# second way
hello(name='Zack')
hello(name='Amy')
```

```python
def profile_info(username, followers):
    print('Username: {}'.format(username))
    print('Followers:  {}'.format(followers))

# Call function with parameters assigned as above
profile_info('JessGarson', 452)

# Call function with keyword arguments
profile_info(username='JessGarson', followers=452)
profile_info(followers=452, username='JessGarson')
```

## Arguments/Parameters/Arguments
Functions take in parameters/arguments.

Parameters are the variables inside the function.

Arguments are the value passed into the function.

```
def something(parameter):
    code goes here
    return value
```

```python
def add_numbers(x, y, z):
    a = x + y
    b = x + z
    c = y + z
    print(a, b, c)

add_numbers(1, 2, 3)
```

## Return Value
The return value is allows us to specify if your function should output a value.

You should end your function with a return statement if the function should output something. Without the return statement, your function will return an object None.

This is what was happening for the previous functions we wrote with the print statements. The None value represents a lack of a datatype.

We can have multiple return values for a function as well.

```python
def plus_one(number):
  return number + 1

plus_one(number=3)
```

```python
def square(x):
    y = x ** 2
    return y

result = square(3)
print(result)
```

## Docstrings
Docstrings help us document what the code does.
```python
def plus_one(number):
  """Adds one to the number"""
  return number + 1


print(plus_one(number=3))
```

## Local and Global Scope
Variables assigned in a function are only local to that function. Variables assigned outside of all functions exist in the global scope. You can have variables named the same thing in different functions that are different variables.

```python
import datetime

time = datetime.datetime.now() # global

def greeting(time):
  name = 'Jess' # local and temporary
  print('Hello {}, the time is {}'.format(name, time))

print(name)
greeting(time=time)
```

```python
import datetime

time = datetime.datetime.now()  # global
name = 'Rachel'


def greeting(time):
    global name
    name = 'Jess'
    print('Hello {}, the time is {}'.format(name, time))


print(name)
greeting(time=time)
print(name)
```

## What was that datetime thing? We never covered imports?

This allows us to import in libraries. Libraries are bundles of other people's code that allow us to do a thing. In this case datetime is part of the standard library and we can import this in if we need.

## Why Not Have Everything Be Global

This allows us to separate out the code so that is easier for debugging. So if something is going wrong you can take a look at the function, instead of looking through the entire program.

## Main Functions
Many other programming languages require a main function in order to execute. Including a `main()` function, though not required, can structure our Python programs in a logical way that puts the most important components of the program into one function. It can also make our programs easier for non-Python programmers to read.

In Python, `__main__` is the name of the scope where top-level code will execute. When a program is run from standard input, a script, or from an interactive prompt, its `__name__` is set equal to `__main__`.

```python
def hello():
    print('Hello, World!')


def main():
    print('This is the main function.')
    hello()


# main()


if __name__ == '__main__':
    main()

# if __name__ == '__main__':
    # hello()
```

## Your Functions They Do Too Much
To make your code more reusable and less error prone. Try to make it so your functions only do one thing at a time. This will allow your code to be more testable in the future.
