# Prime Factors Sieve Of Eratosthenes

##Learning Competencies

* Use Pseudocode
* Implement algorithms

##Summary

In this challenge, we'll be implementing a much more sophisticated version of our previous `prime_factors` function using one of the oldest algorithms know, the [Sieve of Eratosthenes](http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes).

To get the prime factors of `n` your old method probably checks all the integers `p` within `1 < p <= sqrt(n)`. That's doing a bunch of extra work. For example, you'll be checking whether 3, 6, 9, 12, 15, etc. all divide your input. Once you know 3 is prime you shouldn't need to check whether 6, 9, 12, or any multiple of 3 divide your input because *by definition* no multiple of 3 will be prime.

The Sieve of Eratosthenes works by iterating through the range of integers you care about and simultaneously ruling out large parts of that range. An image:

![Sieve of Eratosthenes](http://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)

This is a relatively advanced challenge and is the most sophisticated algorithm you've implemented yet, most likely. Focus on understanding the algorithm–Eratosthenes certainly did it on paper, and so should you!

##Releases

###Release 0 : Implement the Sieve of Eratosthenes

Write a method `erastothenes_sieve` which takes as its input an integer `n` and returns all prime numbers `p` such that `1 < p <= n`.

###Release 1 : Refactor `prime_factors`

Refactor your `prime_factors` implementation to take advantage of the Sieve of Eratosthenes.

<!-- ##Optimize Your Learning -->

##Resources

* [Sieve of Eratosthenes](http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)