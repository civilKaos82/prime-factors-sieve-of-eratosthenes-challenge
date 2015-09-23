# Prime Factors: Sieve Of Eratosthenes

## Summary
In this challenge we're going to refactor a working solution to the *[prime-factors-challenge][]* that we've previously completed.  A working codebase has been provided.  We're going to refactor the code to use a specific algorithm for iterating over the possible prime factors of a number.

### Sieve of Eratosthenes 
We're going to refactor the provided code to use one of the oldest algorithms know, the [Sieve of Eratosthenes][].

In the codebase we'll be working with, to find a prime factor of a given number, we run through all the numbers between one and that given number until we find a prime factor.  We check one, then two, then three, four, five, six, etc.

With this approach, we do a lot of unnecessary work. For example, we'll check is a given number is divisible by two.  And then we'll check to see if the number is divisible by four, six, eight, and all the other even numbers in the range.  But we know that if a number were divisible by four, six, or eight, it would have already been found to be divisible by two.  Said the other way, if the number was not divisible by two, it won't be divisible by any other even number.

And we do the same thing with three when we later check six, nine, twelve, etc. And the same again for five, checking then ten, fifteen, twenty, etc.

![Sieve of Eratosthenes](http://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)

*Figure 1*.  Using the Sieve of Eratosthenes to find a collection of prime numbers less than 121.

The Sieve of Eratosthenes helps us by creating a collection of prime numbers that we could iterate over to avoid this unnecessary work.  Wikipedia provides an [overview][SoE overview] of how to create the collection of numbers, which has been translated into the following steps.  Figure 1 depicts this process visually.

1. Create a list of consecutive integers from 2 through *n*:  2, 3, 4, ... *n*.
2. Take the first number in the list (i.e., 2) and remove all of it's multiples (e.g., 4, 6, 8, 10, etc.).
3. Take the next remaining number in the list (i.e., 3) and remove all of it's multiples from the list.
4. Repeat Step 3 until all numbers in the list have been checked. 


##Releases

###Release 0 : Implement the Sieve of Eratosthenes

Write a method `erastothenes_sieve` which takes as its input an integer `n` and returns all prime numbers `p` such that `1 < p <= n`.

###Release 1 : Refactor `prime_factors`

Refactor your `prime_factors` implementation to take advantage of the Sieve of Eratosthenes.

<!-- ##Optimize Your Learning -->

##Resources

[prime-factors-challenge]: ../../../prime-factors-challenge
[Sieve of Eratosthenes]: http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes
[SoE overview]: https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes#Overview
