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

## PHP Linter

Let's start off strong and get set up with a linter for PHP.

```bash
apm install linter-php
```

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
for ($i = 1; $i <= 10; $i++)
{
  echo $i;
}
```

## Functions

Functions in PHP are named in camel case (no `$` here). The arguments they take
do have the same syntax as variables, though.

If `return` is not explicit, functions in PHP return `NULL`.

Basic function structure:

```php
function add($a,$b)
{
  return $a + $b;
}
add(10,20);
```

## Lab: Build a Calculator

In [lib/calculator.php](lib/calculator.php), create a calculator function that
takes two parameters. The first should be the operation to be completed
(`addition`, `subtraction`, `multiplication`, `division`). The second and third should be two values to operate on.

If you want to peek ahead at arrays in PHP, instead of passing in two numbers
as arguments, pass in an array of varying length to operate on.

To run a PHP script from the command line:

`php <filename.php>`

> In `calculator.php` you'll notice a `<?php` tag. Feel free to read more about that here: [http://php.net/manual/en/language.basic-syntax.phptags.php](http://php.net/manual/en/language.basic-syntax.phptags.php)

## Arrays

Arrays in PHP are very different compared to JavaScript and Ruby arrays.

To quote [PHP Manual](http://php.net/manual/en/language.types.array.php):

> An array in PHP is actually an ordered map. A map is a type that associates
> values to keys. This type is optimized for several different uses; it can be
> treated as an array, list (vector), hash table (an implementation of a map),
> dictionary, collection, stack, queue, and probably more. As array values can
> be other arrays, trees and multidimensional arrays are also possible.

```php
$arr = array(
    'key1'  => 1,
    'key2' => 2,
    'key3' => 3,
);
echo $arr['key1'];
```

## Lab: FizzBuzz

In [lib/fizzbuzz.php](lib/fizzbuzz.php), build FizzBuzz from scratch. Create an
array containing keys `fizz`, `buzz`,`fizzbuzz`, and `other`, each with arrays
as values. As you iterate through all the numbers from 1 to `$maxNum`, push
each number into one of the lists mentioned above;

Numbers divisible by 3 only should go into the `fizz` array, numbers
divisible by 5 only should go into the `buzz` array, numbers divisible by both
should go into the `fizzbuzz` array, and numbers divisible by neither should go
into the "other" array. Finally, once you're done, print the resulting
array to check that your code runs properly.

## Additional Resources

-    [PHP Manual - Official Docs](http://php.net/manual/en/)

## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
