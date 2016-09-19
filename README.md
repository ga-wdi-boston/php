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

In PHP, there is minimal difference between using `" "` or `' '` for strings.

### String Interpolation

`" "` in PHP allows us to evaluate expressions within strings.

```php
$str = "test";
echo "This is a $str"; # => "This is a test"
echo 'This is a $str'; # => "This is a $str"
```

This allows us one option for string concatenation. Another in PHP is by using
`.`. This operator would be used in the same fashion as `+` with JavaScript
interpolation.

```php
$str = "test";
echo "This is a " . $str; # => "This is a test"
```

## Flow Control

### Conditionals

PHP conditional statements are practically identical to JavaScript's.

```php
if (1 > 2)
{
	echo "this";
}
elseif (2 > 3)
{
	echo "that";
}
else
{
	echo "phew";
}
```

One stylistic difference you'll start noticing with PHP is that blocks (`{}`)
typically open on a new line.

### Loops

Again, just like JavaScript!

`while`:

```php
while ( $i < 10 )
{
  echo $i;
  $i++;
};
```

`for`:

```php
for ($i = 1; $i <= 10; $i++) {
  echo $i;
}
```

## Functions

Functions in PHP are named in camel case (no `$` here). The arguments they take
do have the same syntax as variables, though.

If `return` is not explicit, functions in PHP return `NULL`.

Basic function structure:

```php
function add($a,$b){
  return $a + $b;
}
add(10,20);
```

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
