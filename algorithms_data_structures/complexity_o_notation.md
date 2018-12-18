# Complexity. O-notation.

## Complexity
Algorithmic complexity is concerned about how fast or slow particular algorithm performs. We define complexity as a numerical function T(n) - time versus the input size n. We want to define time taken by an algorithm without depending on the implementation details. But you agree that T(n) does depend on the implementation! A given algorithm will take different amounts of time on the same inputs depending on such factors as: processor speed; instruction set, disk speed, brand of compiler and etc. The way around is to estimate efficiency of each algorithm asymptotically. We will measure time T(n) as the number of elementary "steps" (defined in any way), provided each such step takes constant time.

Let us consider two classical examples: addition of two integers. We will add two integers digit by digit (or bit by bit), and this will define a "step" in our computational model. Therefore, we say that addition of two n-bit integers takes n steps. Consequently, the total computational time is T(n) = c * n, where c is time taken by addition of two bits. On different computers, additon of two bits might take different time, say c1 and c2, thus the additon of two n-bit integers takes T(n) = c1 * n and T(n) = c2* n respectively. This shows that different machines result in different slopes, but time T(n) grows linearly as input size increases.

The process of abstracting away details and determining the rate of resource usage in terms of the input size is one of the fundamental ideas in computer science.

## O-notation

Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. It is a member of a family of notations invented by Paul Bachmann, Edmund Landau, and others, collectively called Bachmann–Landau notation or asymptotic notation.

In typical usage, the formal definition of O notation is not used directly; rather, the O notation for a function f is derived by the following simplification rules:

If f(x) is a sum of several terms, if there is one with largest growth rate, it can be kept, and all others omitted.
If f(x) is a product of several factors, any constants (terms in the product that do not depend on x) can be omitted.
For example, let f(x) = 6x^4 − 2x^3 + 5, and suppose we wish to simplify this function, using O notation, to describe its growth rate as x approaches infinity. This function is the sum of three terms: 6x^4, −2x^3, and 5. Of these three terms, the one with the highest growth rate is the one with the largest exponent as a function of x, namely 6x^4. Now one may apply the second rule: 6x^4 is a product of 6 and x^4 in which the first factor does not depend on x. Omitting this factor results in the simplified form x^4. Thus, we say that f(x) is a "big-oh" of (x^4). Mathematically, we can write f(x) = O(x^4). One may confirm this calculation using the formal definition: let f(x) = 6x^4 − 2x^3 + 5 and g(x) = x^4. Applying the formal definition from above, the statement that f(x) = O(x^4) is equivalent to its expansion,

### Examples
#### Constant Time: O(1)
An algorithm is said to run in constant time if it requires the same amount of time regardless of the input size. Examples:

- array: accessing any element
- fixed-size stack: push and pop methods
- fixed-size queue: enqueue and dequeue methods

#### Linear Time: O(n)
An algorithm is said to run in linear time if its time execution is directly proportional to the input size, i.e. time grows linearly as input size increases. Examples:

- array: linear search, traversing, find minimum
- ArrayList: contains method
- queue: contains method

#### Logarithmic Time: O(log n)
An algorithm is said to run in logarithmic time if its time execution is proportional to the logarithm of the input size. Example:

- binary search
Recall the "twenty questions" game - the task is to guess the value of a hidden number in an interval. Each time you make a guess, you are told whether your guess iss too high or too low. Twenty questions game imploies a strategy that uses your guess number to halve the interval size. This is an example of the general problem-solving method known as binary search:

*Note, log(n) < n, when n→∞. Algorithms that run in O(log n) does not use the whole input.*

#### Quadratic Time: O(n2)
An algorithm is said to run in logarithmic time if its time execution is proportional to the square of the input size. Examples:

- bubble sort, selection sort, insertion sort

