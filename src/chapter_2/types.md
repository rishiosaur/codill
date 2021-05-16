# Primitive Types

Let's go back to the first function that you wrote in JS: `console.log('hello')`. All that this function does is log out 'hello' to the console through what's known as a function call (we'll get to those later). However, it wouldn't function if not for the little word in between the two quotes: `'hello'`. This is an example of a _primitive type_ in JavaScript.

> In programming, a _type_ is just a piece of data that represents something. In the real world, a car is a _type_ of vehicle, and 3 is a type of number. JS has similar constructs to be able to perform operations. For instance, storing a number in memory allows you to add other numbers to it; this is an operation that can only be done between two values of type `number`.
>
> A "primitive" type is the most basic type in the language.



In JavaScript, there are a few basic (primitive) types that you should know about: numbers, strings, `null`, `undefined`, `boolean`s, and `Symbol`s.

## Numbers

Quite obviously, a value of type `number` in JavaScript is, well, a number. There are two sub-types that you should know about: integers and floats.

Integers are what you would represent the _natural_ numbers with: numbers like 1, -3, 16, and so on are integers, but something like 3.14 is not. Anything with a decimal is called a floating-point number, or float for short.

In your terminal, run `node` to start up your REPL. To start playing around with numbers in JS, try typing in a few:

```
$ node
> 3
3
> 15
15
> -15.32
```

You can also try doing some basic operations on numbers:

```
> 15 + 3
18
> 19.5 + 0.4
19.9
> -4 * 5 + 3
-17
```

Here are all of the basic operators that you can perform on two numbers:

- Addition/Subtraction with `+` and `-`
- Multiplication/Division with `*` and `/`
- Exponentiation with `**` (an equation like \\( 2^5 \\) might be represented by `2**5`)

JavaScript operations also supported boosted operation precedence. By default, operations are right-associated, with precedence following from basic BEDMAS rules. For instance, if you wanted to evaluate an expression that looked something like: \\( 20 - [3 \times (2 + 4)] \\), you could run `> 20 - (3 * (2 + 4))`.

## Strings

Numbers are fun to use, but what if you wanted to represent something a little bit more complex, like a piece of text? This is where the `string` type comes in.

Strings are just sequences of UTF-8 encoded characters stored in memory.

> UTF stands for Unicode Transformation Format, and is a simple form of representing text and characters using binary numbers. Computers have to store data in particular ways—we use 1s and 0s at the lowest level of computing, and using UTF-8 gives programmers an efficient way to encode characters into numbers for storage in memory.

In JavaScript, strings can be defined by using 3 types of quotations: `'`, `"`, and the backtick character ("`").

```
> "Hello there!"
Hello there!
> 'Heyo.'
Heyo.
> `Greetings, human!`
Greetings, human!
```

Just like numbers, you can perform certain operations on strings.

Adding two strings together using `+` is called string concatenation (usually shortened to concat), and joins two strings together:

```
> 'hello' + ' ' + 'there'
'hello there'
```

JavaScript is also a dynamic language, which means that its type safety rules aren't very strict. This means that you can also use other types of values in string operations! For instance, if we wanted to show the result of a numeric addition in JavaScript, we could write something like:

```
> 'The result of 1 + 2 is: ' + (1 + 2)
'The result of 1 + 2 is: 3'
```

> The process of changing types in programming is known as type *casting* (or just casting for short). In the above code snippet, we first add 1 to 2, then cast the result to type `string`.

It is here that we also start to discover some of the flaws of JavaScript. Dynamic typing gives us powerful ways to write concise programs, but the rules that govern types also become a bit odd. Let's see what happens if we remove the parenthesis from the code snippet above:

```
> 'The result of 1 + 2 is: ' + 1 + 2
'The result of 1 + 2 is: 12'
```

...what just happened? Instead of getting the result of 3 in the string, we get 12.

This might seem weird at first glance, but think back to the section on Numbers in JavaScript. When evaluating expressions, JS will go from left to right—just like in math. The first thing that JS sees is: `'The result of 1 + 2 is: ' + 1`, and so it casts the number `1` to a string and adds it to the first string, then repeats the process for the second number.

These kinds of errors are quite common when writing JavaScript, and it's always important to think programs through before getting flustered.

Let's try doing some more interesting operations with numbers. What if we wanted to add a `string` that contains a number to a `number`?

```
> 2 + '2'
'22'
```

This illustrates another important part of JavaScript's type casting rules: you cannot cast down types. Strings are not guaranteed to be numbers, which is why instead of casting the string to a number and adding the two as `number` types, the `number` gets casted to a `string`, and the two get concatenated.

A string's value might not always be a number, but a number can *always* be a string: numbers are just sequences of characters, after all.

You can get a specific character of a string by adding square brackets with an index after a string:

```
> 'hello there'[0]
'h'
> 'hello there'[3]
'l'
> 'hello there'[10]
'e'
```

Strings are *zero-indexed*, which means that the first character has index 0. In the code snippet above, accessing the character at index 0 returns `'h'`, which is indeed the first character in the sequence.

To get the length of a string, you can use the `.length` *property* of string types. Don't worry about what that means just yet—just think of it as an associated value of a given type. We'll be looking at properties a little bit more in [Section 2.6 and further](/chapter_2/objects.html).

```
> 'hello there'.length
11
```

`.length` returns a value of type `number`, and we can use this to do some interesting calculations! Remember when I said that strings are zero-indexed? That means that the last character of the string will always be at the index of the length of the string minus one:

```
> 'hello there'.length - 1
10
> 'hello there'[10]
'e'
> 'hello there'['hello there'.length - 1]
'e'
```

If this seems a little bit repetitive, that's because it is. There are ways to get around this repetition called *variables*, but we'll be getting to that in the next section.

To make strings lowercase, you can use their `.toLowerCase()` method (a type of property that's a function):

```
> 'Hey There'.toLowerCase()
'hey there'
```

There's also `.toUpperCase()`, which does exactly what you think it might do: it makes a string uppercased!

```
> 'hello there'.toUpperCase()
'HELLO THERE'
```

We can use `.replace(old, new)` to replace certain pieces of a string with others:

```
> 'hello there'.replace('hello', 'hey')
'hey there'
```

To search a string, we can use `.search(str)`, which returns the index of the given search query (and returns `-1` if it isn't found):

```
> 'hello there'.search('h')
0
> 'hello there'.search('ello')
1
> 'hello there'.search('not found')
-1
> 'hello there'.search('th')
6
```

To get a subselection of a string, we can use `.slice(start, end)`, where `start` and `end` are indices of the given string. `start` is 0-indexed, while `end` is 1-indexed. To capture the string from a given index to the end, you can supply one parameter to `.slice` (just the first one):

```
> 'hello there'.slice(0, 3)
'hel'
> 'hello there'.slice(0, 5)
'hello'
> 'hello there'.slice(3)
'lo there'
```

We can repeat (or multiply) strings by using the `.repeat(n)` method:

```
> 'hello there'.repeat(3)
'hello therehello therehello there'
```

All functions that return the same type are chainable (which means that you can easily repeat them or run them sequentially):

```
> 'hello there'.repeat(3).toUpperCase()
'HELLO THEREHELLO THEREHELLO THERE'
```

## Boolean

Since computer programs deal in binary, what happens if we want to represent a value that's either true or false? This is where values of type `boolean` come in.

There are two values that correspond to `boolean`s: `true` and `false`, which are *reserved keywords* in JS.

> A *reserved keyword* is just a word or a piece of text that the language uses for its own features. You can define keywords of your own using variables (which we'll see later), but certain words in the language (like `true` and `false`) are reserved by the language, and cannot be redefined.

```
> true
true
> false
false
```

Pretty simple, right? Booleans are used primarily as ways to compare values. For instance, we can compare if two values are equal to each other using the `===` operator, which outputs a boolean:

```
> 1 === 2
false
> '1' === 1
false
```

There are a whole host of other operators that we can use to compare values and output booleans.

There are two equality operators in JS: `===` and `==` (we saw the former in the last code snippet). Fundamentally, they do the same thing: check if two values are equal. However, the operator with 3 equal signs also checks the *type* of the values that are being passed. `===` is aptly named the strict equality operator, and `==` is dubbed the loose equality operator:

```
> '1' === 1
false
> '1' == 1
true
```

Similarly, we can check if two values are not equal to each other using the strict inequality check `!==` and the loose inequality operator `!=`:

```
> 1 != 2
true
> 1 != '2'
true
```

We can also compare numbers using the `>`, `<`, `<=` and `>=` operators, which correspond to 'greater than', 'less than', 'less than or equal to', and 'greater than or equal to' respectively:

```
> 3 > 2
true
> 3 >= 3
true
> 1 < 2
true
> 2 > 3
false
```

We can also use the logical comparison operators `&&` and `||`, which are the AND and OR comparators respectively. We use these to compare between booleans:

```
> true || false
true
> true && false
false
> 3 > 2 && 1 > 2
false
> 3 > 2 || 1 > 2
true
```

The negation operator `!` also exists:
```
> !true
false
> !false
true
> !!false
false
```

Other values can be implicitly casted to booleans as well. If a value can be casted to `true`, we call it *truthy*. If it casts to `false`, we call it *falsy*.

Generally, values that represent nothing or 0 get casted to `false`, and values that *do* represent something get casted to `true`. To convert a value to a boolean, you can use double negation (`!!`) or the `Boolean(value)` function:

```
> !!''
false
> !!0
false
> Boolean('')
false
> Boolean(0)
false
> Boolean(3230)
true
> Boolean(' ')
true
```

Don't worry if you can't remember all the type casting rules right now—as you use JS more and more, it'll just become second nature to you (and you'll build more efficient programs along with it).

## Null and undefined

There are two other important reserved keywords that will pop up ofte when writing JavaScript: `null` and `undefined`, and they have the same underlying purpose: to represent nothing at all.

Both are falsy, and they are equal to each other:

```
> Boolean(undefined)
false
> Boolean(null)
false
> undefined == null
true
```
While they might seem to be the exact same, there are some subtle differences. `null` represents literal nothingness: if you're instantiating a value, you can pass `null` as a primitive value. However, if something's been declared but hasn't been defined, `undefined` will be returned.

The key difference between the two is that `null` is meant to be used as an actual value that you can pass around, and `undefined` just represents the abscence of a definition—you shouldn't use it manually in programs too often as a developer.

## Symbol

The last of the primitive type is also one of the most interesting and complex. The `Symbol` type is meant to represent nothing more than a unique value; all things considered, this is also the one that will pop up the least in your daily development needs.

```
> Symbol() === Symbol()
false
> Symbol()
Symbol()
```

These don't get used too often on their own, but when combined with things like arrays and objects, can be extremely useful when tracking entities. Don't worry if you don't completely understand this year—it's perfectly natural. Most professional JS devs go their whole careers barely using this primitive type.