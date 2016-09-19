[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# PHP

Hey, Polyglots! Ready for another programming language?

## Prerequisites

-   [php-guide](https://www.github.com/ga-wdi-boston/php-guide)

## Objectives

By the end of this, developers should be able to:

-   Contrast basic language features and types from PHP with basic language
    features and types from JavaScript and Ruby.
-   Write a simple script in PHP.

## Preparation

1.  [Fork and clone](https://github.com/ga-wdi-boston/meta/wiki/ForkAndClone)
    this repository.
1.  Create a new branch, `training`, for your work.

## Core Syntax, Variables, and Operators

### Syntax

Syntax in PHP is very similar to JavaScript.

Variables use camel case, blocks are held within `{}`, and statements are
terminated by semicolons (`;`).

### Variable Declaration

Variable declaration in PHP is extremely similar to JavaScript's.

Variables can be declared and defined, or declared and defined later.

```php
$str;
$str = "test";
```

Notice those dollar signs(`$`)? Those are used for variable declaration,
similar to how `let` or `const` is necessary in JavaScript. When calling
variables, `$` still precedes the variable's name.

```php
echo $str;
```

> `echo` in PHP will print a value.

### True and False

In PHP, true and false are represented by `TRUE` and `FALSE`. These are both
case insensitive, so `true` and `false` do work, but are against convention.

The falsy values of PHP are:

`FALSE` `NULL` `0` `0.0` `"0"` `''` `[]`

A useful builtin for getting the something's type in PHP is `gettype()`;

```php
$havingFun = TRUE;
echo gettype($havingFun);
```

### Operators

|                      |        JavaScript                   |        PHP               |
|:---------------------|:------------------------------------:|:---------------------------:|
| logical operators    | `&&`, <code>&#124;&#124;</code>, `!` |  `&&`, <code>&#124;&#124;</code>, `!` |
| relational operators | `===` `!==` `>` `<` `>=` `<=`        | `==` `!=` `>` `<` `>=` `<=` |
| arithmetic operators | `+`, `-`, `*`, `/`, `%`              | `+`, `-`, `*`, `/`, `%`     |


## Lab: Practice Using Operators

Let's get used to these operators.

In your PHP REPL, take some time to practice each logical, relational and
artithmetic operator listed for you above.

## Strings

In Python, there is no difference between using `" "` or `' '`.
[Escape Characters](http://python-reference.readthedocs.io/en/latest/docs/str/escapes.html)
are evaluated in both.

```python
>>> print "This is a \n new line."
# => This is a
# => new line.

>>> print 'This is a \n new line.'
# => This is a
# => new line.
```

### String Interpolation

Like Ruby, there are many options for string interpolation in Python. For our
purposes, we'll be using `.format()`, as it is preferred for Python 3.5.

`.format()` is appended to a string and takes a parameters the strings to be
concatenated. If the string contains empty `{}`s, the parameters fill the `{}`s
in the order passed in. If they contain a number (beginning with 0), they will
be mapped to the parameter passed to `.format()` at said index.

```python

>>> awkward_nerd = "Lauren"
>>> awesome_nerd = "Jason"
>>> occupation = "consultant"

>>> "{} is a pretty cool {}.".format(awkward_nerd, occupation)
# => "Lauren is a pretty cool consultant."

>>> "{0} is a {1}. {2} is a {1} as well.".format(awkward_nerd, occupation, awesome_nerd)
# => "Lauren is a consultant. Jason is a consultant as well."
```

## Flow Control

### Conditionals

Again, colons and whitespace are critical to working Python code. Aside from
that and the use of `elif` vs. `elsif`, these should feel very similar to Ruby
conditional statements.

```python
if x < 0:
  print 'Negative'
elif x == 0:
  print 'Zero'
else:
  print 'Positive'
```

### Loops

Also like Ruby, Python employs `while` and `for` loops.

Python also allows for an optional `else` statement with each of these. With
`while` loops, the `else` statement is executed once the `while` condition is
no longer true. With `for` loops, `else` is executed upon the loop's
completion.

```python
count = 0
while count < 5:
   print count, " is  less than 5"
   count = count + 1
else:
   print count, " is not less than 5"
```

```python
count = 15
for i in range(1,count):
  print i
else:
  print "done"
```

Again, this `else` is optional and different in nature from a conditional else.
It functions more as a completion handler.

## Functions

Functions in Python are similar to Ruby methods (Python also has methods, but
we only refer to them as such when they are functions of a Class).

Aside from syntactical differences, the main difference to note is the need for
an **explicit return**. Think JavaScript!

Basic function structure:

```python
def function_example(param_one, param_two):
  """Example function returning string interpolation of parameters."""
  concat = "What a splendid function! I've got my {0} and {1}.".format(param_one, param_two)
  return concat
```

#### Brief Aside: Docstrings

You may have noticed something like

`"""This function..."""`

within each of our example functions. These are called `docstrings` and are
conventionally used in Python to provide documentation throughout a codebase.
Code will run fine without them, but that would stray from Python's conventions
as well as throw you into linter message hell. Try them out!

## Lab: Build a Calculator

In [lib/calculator.py](lib/calculator.py), create a calculator function that
takes two parameters. The first should be the operation to be completed
(`addition`, `subtraction`, `multiplication`, `division`). The second should be
a list with the appropriate number of numbers to operate on. The function
mapped to the appropriate operation should take the expected numbers by index
from the list passed in and return back to you the result of the operation.

We haven't discussed lists yet, but they are very similar to Ruby arrays. The
syntax required for this is very similar to how you would approach this in
Ruby. Lean on the knowledge you gained from the [Python vs Ruby study](https://github.com/ga-wdi-boston/python-vs-ruby-study/)!

Remember, to run a Python script from the command line:

`python <filename.py>`

## Collections

### Lists

Python lists are comparable to Ruby arrays. They store comma separated values
of varying data types between square brackets `[]`.

Lists are ordered, thus, indices can be leveraged to get or set their elements.

```python
wdi_base_langs = ["JavaScript", "Ruby", "SQL"]
wdi_base_langs[2] # => "SQL"
wdi_base_langs[0] = "JS" # => ["JS", "Ruby", "SQL"]
```

`len()` is used to get the length of a list in Python.

```python
len(wdi_base_langs) # => 3
```

We can merge lists together using the `+` operator:

```python
wdi_new_langs = ["Python"]
all_wdi_langs = wdi_new_langs + wdi_base_langs # => ["JS", "Ruby", "SQL", "Python"]
```

#### List Methods

We could have gone about adding "Python" to the end of the `wdi_base_langs`
list by using `.append()`.

```python
wdi_base_langs.append("Python") # => ["JS", "Ruby", "SQL", "Python"]
```

Like Ruby, `.pop()` removes the last element from a Python list. `.append()`
will add to the end of a list.

We do not have built-in operators for removing or adding to the beginning of a
list. As hackers, we've got some hacks, though.

`.remove()` allows us to remove an element at any index. Thus, `list.remove(0)`
would remove the first element from a list.

We could implement our array merging to add to the beginning of a list. Look at
the following:

```python
a = "first"
b = ["second", "third"]
[a] + b # => ["first", "second", "third"]
```

#### Looping Through Lists

`for` loops with lists don't stray far from the loops we saw earlier.

```python
all_wdi_langs = ["JS", "Ruby", "SQL", "Python"]

for lang in all_wdi_langs:
  print lang
```

### Dictionaries

Python dictionaries are very similar to other key-value objects we've seen.

Dictionary keys **must** be unique. Creating a key-value pair for a key that
already exists will simply reassign the value of the existing key.

Keys can be either strings or numbers.

There are two ways of instantiating a Python dictionary:

```python
new_dict = dict()   # => {}
# or
new_dict = {}       # => {}

example_dict = {
  "key_one": "val one",
  "key_two": "val two",
  "key_three": "val three"
}
```

To add or retrieve a key-value pair, we implement square bracket notation:

```python
new_dict["fun_key"] = "fresh"
new_dict["fun_key"]    # => "fresh"
```

`.get()` is another option for retrieving a key's value.

```python
new_dict.get("fun_key") # => "fresh"
```

Dictionary defaults are a little different from Ruby. If it is unknown that a
key you are retrieving exists, you can call `.get()` with a default value
should it not exist.

```python
new_dict.get("no_key", "not there") # => "not there"
```

## Lab: Revamp FizzBuzz

In [lib/list_and_dict_buzz.rb](lib/list_and_dict_buzz.rb), build a more robust
FizzBuzz from scratch. Create a dictionary containing keys `fizz`, `buzz`,
`fizzbuzz`, and `other`, each with lists as values. As you iterate through all
the numbers from 1 to max_num, add each number to one of the lists mentioned
above; numbers divisible by 3 only should go into the `fizz` list, numbers
divisible by 5 only should go into the `buzz` list, numbers divisible by both
should go into the `fizzbuzz` list, and numbers divisible by neither should go
into the "other" list. Finally, once you're done, print the resulting
dictionary to check that your code works properly.

## Additional Resources

-    [PHP Docs](http://php.net/manual/en/)

## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
