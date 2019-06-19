[Computational Neuroscience Crash Course (2019)](https://github.com/rougier/NeuroComp-Bordeaux-2019) —
Arthur Leblois (CNRS) & Nicolas P. Rougier (Inria)<br/>

# Introduction

We introduce here Python, a powerful and easy to learn programming language. It
has *efficient high-level data structures and a simple but effective approach
to object-oriented programming* (Python website). However, we'll only
cover the strict minimum necessary for getting started with numerical computing.

<br/>

**Contents**
* [Objectives](#objectives)
* [First steps](#first-steps) 
* [Types & variables](#types--variables)
* [Control flow](#control-flow)
* [Functions](#functions)

<br/><br/>

## Objectives

The primary goals of this lesson are:

* To introduce Python types & manipulations
* To start programming moderately complex scripts
* To be able to read and write files 
  
<br/><br/>


## First steps

Let's start with simple arithmetic operations because Python can be used as a
regular calculator with standard arithmetic operations (addition, subtraction,
multiplication, division, etc.)

#### Addition

```pycon
>>> 2 + 3
5
```

#### Subtraction

```pycon
>>> 11 - 3
8
```

#### Multiplication

```pycon
>>> 3 * 4
12
```

#### Division

```pycon
>>> 11 / 5
2.2
```

#### Integer division

```pycon
>>> 11 // 5
2
```

#### Modulo operation

```pycon
>>> 11 % 5
1
```

#### Power

```pycon
>>> 2**3
8
```

Note that you cannot have spaces between digits of a number:

```pycon
>>> 1 0 + 2 
  File "<stdin>", line 1
    1 0 + 2
      ^
SyntaxError: invalid syntax
```

In such a case, Python complains about a syntax error and points at the
position of the error in the expression (using the `^` character). Why Python
points at the zero and not the space ? Because you could have written `1 + 2`
and the space would have been legal. The interpreter can only find the error
after it discovers the extra digit and consequently points at it when reporting
the error.

Of course, you can compose any number of operations in order to compute a more
complex operation:

```pycon
>>> 11 - (5 * (11//5)) #  = 11 % 5
1
```


###  Native numeric types

Python offers natively four main native numeric type, `bool`, `integer`,
`float` and `complex`. But always keep in mind that they are the poor's man
version of their mathematical equivalent (Boolean (𝔹), Integer (ℤ), Real (ℝ)
and Complex (ℂ)): `ìnteger` have limited range, `float` and `complex` have
limited range and precision.

In the case of `float` and `complex`, this has very important consequences.

``` pycon
>>> 0.1 + 0.1 + 0.1 == 0.3
False
```

The reason is that decimal numbers `0.1` and `0.3` cannot be represented
exactly and are only approximated. On most machines, if Python were to print
the actual value of the approximation, it would have to display:

```pycon
>>> print("{0:.64f}".format(0.1))
0.1000000000000000055511151231257827021181583404541015625000000000
>>> print("{0:.64f}".format(0.3))
0.2999999999999999888977697537484345957636833190917968750000000000
```

Consequently, Python (as many other languages) chose to display a rounded value
instead. If you want to know more, have a look at the [Floating Point
Arithmetic: Issues and
Limitations](https://docs.python.org/3/tutorial/floatingpoint.html) chapter in
the official [Python 3
tutorial](https://docs.python.org/3/tutorial/index.html). An immediate and
practical consequence is that what you see in the console is not always what
you get in memory, even if they're reasonably close. If you want to know more
about that, make sur to read [What Every Computer Scientist Should Know About
Floating-Point
Arithmetic](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html),
David Goldberg, Computing Surveys, 1991.


The right way to compare float numbers is thus to check if the difference is
below a given threshold:

``` pycon
>>> (0.1 + 0.1 + 0.1) - 0.3 < 1e-15
True
```


For each type, there exist many ways to specify the same number.

``` pycon
>>> True              # Boolean
>>> 0b1010            # Integer (base  2: binary)
>>> 0o12              # Integer (base  8: octal)
>>> 10                # Integer (base 10: decimal)
>>> 0x0a              # Integer (base 16: hexadecimal)
>>> 10.0              # Float
>>> 1e1               # Float (scientic notation)
>>> float('inf')      # Float (infinity +∞)
>>> float('nan')      # Float (Not A Number: nan)
>>> 10 + 0j           # Complex
```

You can also force the type of a quantity by casting it into a different type:

```pycon
>>> bool(0)
False
>>> int(0)
0
>>> float(0)
0.0
>>> complex(0)
0j
```


### Beyond simple arithmetic

If you want to use more elaborate functions, you'll need the help of the
[mathematical module](https://docs.python.org/3/library/math.html) for real
numbers and the [complex mathematical
module](https://docs.python.org/3/library/cmath.html) for complex numbers. To
do that, we have to `import` a library and to use its name as a prefix, in
front of the functions we want to use. For those who know Python, you might
have been tempted to write `from math import *` but this is almost always a bad
idea.


**Power and logarithmic functions** 

```pycon
>>> import math
>>> math.log( math.exp( 1.234 ) )
1.234
```

**Trigonometric functions**

```pycon
>>> import math
>>> math.asin( math.sin( 1.234 ) )
1.234
```

**Hyperbolic functions**

```pycon
>>> import math
>>> math.asinh( math.sinh( 1.234 ) )
1.234
```

**Special functions**

```pycon
>>> import math
>>> math.gamma( 2.0 )
1.0
```

**Constants**

```pycon
>>> import math
>>> math.pi
3.141592653589793
>>> math.e
2.718281828459045
>>> math.nan # Not A Number
nan
>>> math.inf # Infinite
inf
```


### Logical operations

Logic is an important part of Python because this allows to manipulate and
compare quantities, including numbers, and we'll see later that it works for
all kind of objects.

```pycon
>>> True and True # Logical and
>>> 42 or 57      # Logical or
>>> 1 == 2-1      # Equality test
>>> 1 != 2        # Inequality test
>>> 1 is 2-1      # Identity test
>>> not 24        # Negation
```

Note that the `is` keyword really means identity (the two terms point to the
same object), it is not a test for equality.

```pycon
>>> 1 is 1.0
False
>>> True is 1
False
>>> True and 1
True
```

### Bitwise operations

Bitwise operations are logical operations that operate a the bit level. They
might be useful in some situations but we won't use them much in this course.

```pycon
>>> 1 | 2   # bitwise or
>>> 1 & 2   # bitwise and
>>> 1 ^ 2   # bitwise xor
>>> 8 << 2  # bitwise left shift
>>> 8 >> 2  # bitwise right shift
>>> ~8	  # bitwise negation
```



<br/><br/>
## Exercises

Before moving to the [next lesson](02-introduction.md), here are some simple
exercises that should take you only a few minutes to solve. If you want the
solution, just type these expression in a Python console.


### Find the type of the following expressions

```
.0
-1
1,
'float(4) + 5'
1e2
1j
math.nan
```

### Are these legal Python expressions?

```
1 + 1 == 2
1 = 2
1 + 1i
1 <- 2
0.+.0
3***3
3 <<2>> 3
```

### Find the result of the following expressions

```
1.+.1
0b1+0xb1
(1,)*3
1e1000 - 1e1000
'abc'*3
3 or 10
3 <2 > 3
```

<details><summary>
Click to see solution
</summary></p>

```
1.+1,            # (2.0,)
1,+1.            # (1, 1.0)
(1,)*3           # (1, 1, 1)
1e1000 - 1e1000  # nan
'abc'*3          # 'abcabcabc'
3 or 10          # 3
3 <2> 3          # False
```

</details>

<br/><br/>


## Types & variables

Beside being a convenient calculator, Python is also (and mostly) a powerful
programming language with an elegant and intuitive syntax. Furthermore, you
have to knwo that Python is an interpreted langage, meaning each time you enter
a set of instructions, they need to be intepreted by the Python interpreter. This
can make Python quite slow in some situation but we'll later how to overcome most
of Python slowness.

### Variables

Until now, we have been playing in the console, throwing some expressions in
the interpreted and checked the result. Problem is that those expression cannot
be re-used. It's thus time to save us some trouble and assign those expressions
to variables. This can be done quite naturally.

``` python
>>> width = 1
>>> height = 2
```

What is really cool though is that you can assign several variables at once:

``` python
>>> width, height = 2,1
>>> width
1
>>> height
2
```

However, you cannot refer a new variable on the same line

``` python
>>> width, height = 2, 2*width
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'width' is not defined
```

In this case, you have to split the expression in two distinct lines.

``` python
>>> width = 2
>>> height = 2*width
```

Variables can be manipulated just as any expression but they need to have been
defined previously.

``` python
>>> a = 2*b
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'b' is not defined
```


### Containers

Beside the numeric types, Python also offers native container type (also known
as collections), one is dedicated to the storage of ordered sequence of
characters (i.e. strings) while some others allows to store just anything and
offer different properties. In a nutshell:

``` python
>>>  "1,2,3,4"  # String (ordered, immutable, iterable, indexable, character only)
>>>  (1,2,3,4)  # Tuple (ordered, immutable, iterable, indexable)
>>>  [1,2,3,4]  # List (ordered, mutable, iterable, indexable)
>>>  {1:2,3:4}  # Dictionnary (unordered, mutable, iterable, keys are hashable)
>>>  {1,2,3,4}  # Set (unordered, mutable, iterable, unique elements)
```

From the [Python glossary](https://docs.python.org/3/glossary.html)

| Property | Definition |
|:-------- |:---------- |
**ordered**   | An object with a natural order between elements
**mutable**   | An object that can change its value.
**immutable** | An object with a fixed value.
**hashable**  | An object usable as a dictionary key and a set member.
**iterable**  | An object capable of returning its members one at a time.
**indexable** | An iterable that supports element access using integer indices


#### Strings

Strings are expressed by enclosing a text using pairs of " or \'
characters. Depending on the character you chose, you can use the other inside
the string.

``` python
>>> "Hello 'world!'"
"Hello 'world!'"
>>> 'Hello "world"!'
'Hello "world!"'
>>> "" # empty string
''
```

Note that you can split a string using spaces and Python will concatenate all
the pieces together.

``` python
>>> "Hello"  " "  "world!"
'Hello world!'
```


But you can also explicitely concatenate the different pieces together.

``` python
>>> "Hello" + " " + "world!"
'Hello world!'
```

For multiline strings, you need to triple the enclosing quotes or to use parentheses.

``` python
>>> """Hello 
... world!"""
'Hello\nworld!'

>>> '''Hello 
... world!'''
'Hello\nworld!'

>>>("Hello"
... " world!")
'Hello world!'
```

In the output above, you can seen the "\n" character has been added, it
expresses the newline character. There are several backslashed characters:

Escape Sequence | Meaning 
----------------|---------------------------
\\\\            | Backslash (\)
\\\'            | Single quote (')
\\\"            | Double quote (")
\a              | ASCII Bell (BEL)
\b              | ASCII Backspace (BS)
\n              | ASCII Linefeed (LF)
\r              | ASCII Carriage Return (CR)
\t              | ASCII Horizontal Tab (TAB)
\v              | ASCII Vertical Tab (TAB)

This means the '\n' will be interpreted as a new line character, but what if we
want to really have '\n' in our string as in 'C:\\some\\name'? Either we
"escape" all the backslash or we prefix the string with `r` meaning special
characters won't be interpeted.

```
>>> print('C:\some\name')
'C:\some
ame'
>>> print('C:\\some\\name')
C:\some\name
>>> print(r'C:\some\name')
C:\some\name
```

Strings in Python 3 are encoded using UTF-8 ([Unicode]), meaning you can encode
pretty much any glyphs fom any languages (and emojis as well).

``` python
>>> "ℕ ⊂ ℤ ⊂ ℚ ⊂ ℝ ⊂ ℂ" 
'ℕ ⊂ ℤ ⊂ ℚ ⊂ ℝ ⊂ ℂ'
```

#### Tuples

Tuples are immutable containers, meaning they cannot be changed after they've
been created. They allow to store pretty much anything, including other tuples.
To create a tuple, you simply write a comma-separated list of values,
optionally enclosed by parentheses.

``` python
>>> 1,2,3
(1, 2, 3)
>>> 1, "2", (1,2) 
(1, '2', (1, 2))
>>> () # empty tuple
()
```

#### Lists

Lists are mutable containers quite similar to tuple, but they can be modified
after creation. They also allow to store pretty much anything. To create a
list, you need to write a comma-separated list of values enclosed by square
brackets.

``` python
>>> [1,2,3]
[1, 2, 3]

>>> [1, "2", (1,2)]
[1, '2', (1, 2)]

>>> [] # empty list
[]
```

#### Sets

Sets are mutable containers (they can be modified) and contains only unique
elements, i.e. they prevent to have duplicated elements.

``` python
>>> {1, 2, 2}
{1, 2}

>>> {1, 2, "2"}
{1, 2, '2'}
```

#### Dictionnary

Dictionnary can be considered as a kind of associative memory where items are
indexed by a key (instead of integer). The type of the key can be pretty much
anything.

``` python
>>> { "item 1" : 1, "item 2" : 2}
{'item 2': 2, 'item 1': 1}
>>> { 1 : 2, 3 : 4}
{1: 2, 3: 4}
```

<br/>

### Indexing and slicing

Individual items of a list, tuple and strings can be accessed invidually using
their position as index. Note that first element has index 0

``` python
>>> d = [1,2,3,4,5]
>>> d[0]
1
```

This also work using negative indices, meaning the position has to be taken
from the end. Note that last element has index -1.

``` python
>>> s = "Hello world!"
>>> s[-1]
'!'
```

Furthermore, we can also access a **range** of items using the slice notation
`start:end`. Note that both start and end are optional.

``` python
>>> d = [1,2,3,4,5]
>>> d[1:3]
[2, 3]
```

If start is missing, Python will implicitly replace it by the start of the
list. If end is missing, Python will implicitly replace it by the end of the
list.


``` python
>>> d = [1,2,3,4,5]

>>> d[1:]
[2, 3, 4, 5]

>>> d[:2]
[1, 2]

>>> d[:]
[1, 2, 3, 4, 5]
```

We can further refine our slice by giving the step to between elements. The new
syntax is thus `start:end:step`.

``` python
>>> d = [1,2,3,4,5,6]
>>> d[0:5:2]
[1, 3, 5]

# Can be abbreviated into
>>> d[::2] # 
[1, 3, 5]
```

What if we use a negative step? We get the reversed sequence.

``` python
>>> d = [1,2,3,4,5,6]
>>> d[::-1] 
[6, 5, 4, 3, 2, 1]
```

Because strings are indexable, indexing and slicing work just the same.


``` python
>>> s = "Hello world!"
>>> s[6:-1]
" world"
>>> s[6:]
" world!"
```

<br/>

### Adding and removing

Adding an element to a mutable container can be done in two distinct
ways. Either by creating a new container that is the container plus the new
item, or by inserting the new item into the container, hence modyfying it.

``` python
>>> l1 = [1, 2, 3]
>>> l2 = l1 + [4]
>>> l2
[1, 2, 3, 4]
>>> l1.append(4)
>>> l1
[1, 2, 3, 4]
```

For removing items, we need to use the **del** instruction and give indices where
to delete items.

``` python
>>> l1 = [1, 2, 3, 4, 5, 6]
>>> del l1[0 ]
>>> l1
[2, 3, 4, 5, 6]
```

But we can also delete a range of indices at once.

``` python
>>> l1 = [1, 2, 3, 4, 5, 6]
>>> del l1[::2]
>>> l1
[2,4,6]
```

Something you will discover soon enough (or maybe you've already discovered it)
is that Python is rather nitpicking about indentation.

``` python
>>> a = 1
>>>  a = 1
  File "<stdin>", line 1
    a = 1
    ^
IndentationError: unexpected indent
```

The reason is that indentation has a semantic meaning but we'll see that later.



<br/>

### Exercises

#### How to...

<details><summary>
... build the empty set?
</summary></p>

```Python
empty = {}    # Wrong: this builds an empty dictionnary
empty = set() # Right
```
</p>
</details>


<details><summary>
... get the list of unique letters composing "abracadabra"?
</summary></p>

```Python
letters = set("abracadabra")
```
</p></details>


<details><summary>
... build a tuple of two empty lists?
</summary></p>

```Python
a = ([], []) # Right but parenthesis are not necessary
a = [], []   # Right
```
</p></details>


<details><summary>
... generate a list of all even numbers between 20 and 40 (included)?
</summary></p>

```Python
numbers = list(range(20, 41, 2)
```
</p></details>

<details><summary>
... check if a word is a palindrom?
</summary></p>

```Python
word = "kayak"
print(word == word[::-1]) # Note that this does not work with "Kayak"

word = "Kayak".lower()
print(word == word[::-1]) # This works thanks to the lower method
```
</p></details>

<details><summary>
... transform the string "1.2" into a float?
</summary></p>

```Python
a = float("1.2)
```
</p></details>

<details><summary>
... count the number of unique elements in a list?
</summary></p>

```Python
mylist = [1,2,3,4,3,2,1]
size = len(set(mylist))
```
</p></details>

<details><summary>
... print the string "Isn't it, he said" (including quotes)?
</summary></p>

```Python
print('''"Isn't it, he said"''')
```
</p></details>

<details><summary>
... swap the content of two variables?
</summary></p>

```Python
a,b = 1,2
a,b = b,a
```
</p></details>



<br/><br/>

<!---------------------------------------------------------------------------->

## Control flow

Control flow is the order in which instruction are evaluated or not evaluated.
This is a very important aspect of programming and it is thus of the utmost
importance to fully understand and masterize it. 

### Conditional execution

One of the simplest way to control flow of execution is to have a condition
that tells Python to execute a block of instruction only if a condition is
true:

```Python
number = 2
if number % 2 == 0:
    print("Number {0} is even".format(number)
```

If you run this small program, you should the string "2 is even" displayed on
your screen. You might have noticed the print function is indented and this is
something really important in Python. Everything that has the same level of
indentation (4 spaces in our case) constitutes a logical block. If we want to
execute more core when the condition is true, we just add new instruction with
the same level:

```Python
number = 8
if number % 2 == 0:
    print("{0} is even".format(number), end="")
    print(" because {0} % 2 == 0".format(number))
```

What if the number is odd? We have to extend our test by telling what to do in
case the first condition is false:

```Python
number = 10
if number % 2 == 0:
    print("{0} is even".format(number))
else:
    print("{0} is odd".format(number))
```

However, the way it is now written, we implicitely assume that if a number is
not even, it is odd. But if you remember the Zen of Python (if not, type
`import this` in a Python shell), you know it is better to make things
explicit rather than implicit:

```Python
number = 1.1
if number % 2 == 0:
    print("{0} is even".format(number))
elif number % 2 == 1:
    print("{0} is odd".format(number))
else:
    print("The arity of {0} is unknown".format(number))
```

You can specify various conditions using any of the logical operators but there
are also some specific Python tests that are very convenient:

```Python
a = 1,2,3
b = 1,2,3
c = a

a == b # True (equality)
a is b # False (identity)
a is c # True (identity)
1 in a # True
```

### Iterations

Another way to control the flow of execution is to ask Python to repeat some
instructions using the
[range](https://docs.python.org/3.7/library/stdtypes.html#ranges) instruction:

```Python
>>> for i in range(3):
...    print(i)
0
1
2
```

The syntax of the range function is `range(stop)` or `range(start,stop,step)`,
this means we can, for example, iterate over even numbers:


```Python
>>> for i in range(0,10,2):
...    print(i)
0
2
4
6
8
```

or in reverse order


```Python
>>> for i in range(50,0,-10):
...    print(i)
50
40
30
20
10
```


### Loops

If you don't konw in advance how many times you want to repeat something, you can use the
[while(condition)](https://docs.python.org/3.7/reference/compound_stmts.html?#the-while-statement) instruction that will repeat a block of instruction while the condition is True. When the condition becomes False, the loop terminates:

```Python
>>> a = 0
>>> while a < 10:
...     a = a+1
>>> print(a)
10
```

Note that in some case you want to terminate the loop early using the `break` statement:


```Python
>>> a = 0
>>> while a < 10:
...     a = a+1
...     if a > 8: break
>>> print(a)
9
```


### Sequences

Since containers are iterable, we can directly use them and write:

```Python
>>> for word in ["cool", "powerful", "readable"]:
...     print("Python is {0}".format(word))
Python is cool
Python is powerful
Python is readable
```

We can even write:

```Python
>>> for (x,y) in [(0,1), (2,3), (4,5)]:
...     print(x,y)
0 1
2 3
4 5
```

Furthermore, because a string is a list of letters, we can also iterate over a
word:

```Python
>>> for c in "Python":
...     print(c)
P
y
t
h
o
n
```

If we want to keep track of the index, Python provodes the `enumerate` function:

```Python
>>> for index,c in enumerate("Python"):
...     print("{0} : {1}".format(index, c))
0 : P
1 : y
2 : t
3 : h
4 : o
5 : n
```


### List comprehension

We can also use iterators to direclty create a list:

```Python
>>> l =  [i**2 for i in range(4)]
>>> print(l)
[0, 1, 4, 9]
```

This is called list comprehension and this is useful in a number of situation.


### Exercise

<details><summary>
Write a program that prints the numbers from 1 to 100. But for multiples of
three print “Fizz” instead of the number and for the multiples of five print
“Buzz”. For numbers which are multiples of both three and five print
“FizzBuzz”.
</summary></p>

```Python
for n in range(1,101):
    if n % 3 == 0 and n % 5 == 0:
        print("FizzBuzz")
    elif n % 3 == 0:
        print("Fizz")
    elif n % 5 == 0:
        print("Buzz")
    else:
        print(n)
```
</p></details>


<details><summary>
Write an infinite while loop that does nothing. How do you terminate your program?</summary></p>

```Python
while True: pass
```

Terminate the program by pressing `CTRL-C` in the console. If you're using the Jupyer notebook, click on the stop button at the top of your browser.
</p></details>



<br/><br/>

<!---------------------------------------------------------------------------->

## Functions

Functions are code snippet that can be defined and called from anywhere in your
program. For example, if you are often doing the same computation, it might be
a good idea to define a function to do this computation and to call this
function when necessary. The advantage of doing so is that the actual
computation is defined in one place where you can control that he computation
is correct. If you don't do that and copy/paste your code snippet everywhere,
you might forget later to change all of them if you find a bug.

### Definition

To define a function, you need a name, a list of arguments (that can be empty)
and some code to be executed when the function is called:

```Python
>>> def hello():
...     print("Hello world!")
>>> hello()
Hello world!
```

The above function does not take any argument and does not return any
value. Let's write a more useful function that, given a radius, return the area
of the corresponding disc:

```Python
>>> def disc_area(radius):
...    return math.pi*radius*radius
>>> a = disc_area(0.5)
>>> print(a)
0.7853981633974483
```

### Mandatory and optional parameters 

A function can take as many arguments as you want and when you call the
function you need to give the value for each of these arguments or Python will
complain. For example, let's try to call the previous function without any
value:

```Python
>>> disc_area()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: disc_area() missing 1 required positional argument: 'radius'
```

Python complains because the value of radius is not defined and consequently,
it cannot compute the area. This means that if your function takes a long
list of arguments, you'll need to define each of them unless you assign them a
*default* value. Let us redefine our `disc_area` function as:

```Python
>>> def disc_area(radius=1.0):
...    return math.pi*radius*radius
```

The difference with the previous version is the `radius=1.0` part. This means
that, if the value of `radius` is not given when the function is called, the
value of radius will be `1.0`. This is called a default value. Let's now try to
call the function without arguments:

```Python
>>> disc_area()
3.141592653589793
```

With these default values, you can call a function without any arguments and
each of them will be assigned the default value. But what if you want to use
the default values for some and your own value for some others ? To do that we
need to call the function with named argument.

```Python
>>> def function(a=1, b=2, c=3):
...     print(a,b,c)
>>> function(b=4)
1 4 3
```

**Note**: Default values are created when the function is defined, not when it
is called. If you have a mutable parameter such as a list and you modify it in
your function, the new value will stay:

```Python
>>> def function(mylist=[]):
...     mylist.append(0)
...     return mylist
>>> print(function())
[0]
>>> print(function())
[0, 0]
>>> print(function())
[0, 0, 0]
```

### Global variables

One important thing to understand regarding function and paremeters is that
they're local to the function and will disappear as soon as the function
terminates:

```Python
>>> x, y, z = 1, 2, 3
>>> def function(x, y, z):
...     x, y, z = 4, 5, 6
...     return x, y, z
>>> function(x,y,z)
>>> print(x,y,z)
1 2 3
```

In the (purposedly confusing) example above the x,y,z inside the function
relates to the argument, not the external variables x,y,z. When we change them
inside the function, we only change them locally. If we want to keep the
result, we have to distinct solutions. For the first solution, we assign the result of the function to the external variables x, y and z:

```Python
>>> x, y, z = 1, 2, 3
>>> def function(x, y, z):
...     x, y, z = 4, 5, 6
...     return x, y, z
>>> x, y, z, = function(x,y,z)
>>> print(x,y,z)
4 5 6
```

Another way is to specify inside the function that we want to modify variables that are external to the functino using the `external` keyword:

```Python
>>> x, y, z = 1, 2, 3
>>> def function():
...     global x, y, z
...     x, y, z = 4, 5, 6
>>> function(x,y,z)
>>> print(x,y,z)
4 5 6
```

### Documentation

Last, but not least on functions, we can (and we will) document them using what
is called a docstring. Let's rewrite a third time our `disc_area` function:

```Python
def disc_area(radius=1.0):
    "Compute the area of a disc with given radius"
    
    return math.pi*radius*radius
```

Now if we want what a function does, we simply type:

```Python
>>> help(disc_area)
```

and we get:

```
Help on function disc_area in module __main__:

disc_area(radius=1.0)
    Compute the area of a disc with given radius
```




### Exercises

Write a function that computes the first `n` terms of the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number).

<details><summary>
Click to see solution
</summary></p>

```
def fibonacci(n):
    "Computer the first n terms of the Fibonacci sequence"
    
    u = [0, 1]
    for i in range(n-2):
        u.append(u[-1]+u[-2])
    return u
```

<br/><br/>




<br/><br/>
## Bibliography


Here are a set of resources for those who want to go further in their knowledge
of Python.

* [**Scipy Lecture Notes**](http://scipy-lectures.org/intro/index.html). This
  part of the Scipy lecture notes is a self-contained introduction to
  everything that is needed to use Python for science, from the language
  itself, to numerical computing or plotting.



* [**The (official) Python tutorial**](https://docs.python.org/3/tutorial/index.html)
  does not attempt to be comprehensive and cover every single feature, or even
  every commonly used feature. Instead, it introduces many of Python's most
  noteworthy features, and will give you a good idea of the language's flavor
  and style.

* [**Dive into python**](http://www.diveintopython3.net) is a teach-by-example
  guide to the paradigms of programming in Python and modern software
  development techniques. It assumes some preexisting knowledge of programming,
  although not necessarily in Python.  
  


<br/><br/>

##  

**Copyright © 2019** Arthur Leblois & [Nicolas P. Rougier](http://www.labri.fr/perso/nrougier) – Released under a [CC-BY 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license.

<!----------------------------- External links ------------------------------->
[Anaconda]:     https://www.anaconda.com
[Python]:       http://www.python.org
[Numpy]:        http://www.numpy.org
[Scipy]:        http://www.scipy.org
[Matplotlib]:   http://matplotlib.org
[IPython]:      http://ipython.org
[Jupyter]:      http://jupyter.org
[Git]:          https://git-scm.com
[Cython]:       http://cython.org
[Unicode]:      https://en.wikipedia.org/wiki/Unicode
[Emacs]:        http://www.emacs.org/
[vim]:          https://www.vim.org/
[Atom]:         https://atom.io/
[Notepad++]:    https://notepad-plus-plus.org/
[Sublime Text]: https://www.sublimetext.com/
<!---------------------------------------------------------------------------->
