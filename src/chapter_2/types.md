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
- Exponentiation with `**` (an equation like \\( \int x dx = \frac{x^2}{2} + C \\))
