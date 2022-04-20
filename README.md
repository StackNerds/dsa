# Data Structures and Algorithms
Notes and projects on data structures and algorithms

### The guessing game

In the guessing game users are expected to guess a number in range. The user with the fewest gueses wins. When the guess is wrong the users are told whether their guess is "too high" or "too low".

Round 1: 

- Winning number is 3
- Range is 1 to 10 (inclusively)

#### Approach one:

A certain user, Ambe, plays the game using the following approach

- Ambe guesses 1 => Too low
- Ambe guesses 2 => Too low
- Ambe guesses 3 => Correct

#### Approach two:

Another user, Lum, plays the game using the following approach

- Lum guesses 5 => Too high
- Lum guesses 2 => Too low
- Lum guesses 3 => Correct

Both Ambe and Lum, takes thesame number of turns to determine the correct answer, so who method is best? Well let's take another try:


Round 2: 

- Winning number is 10
- Range is 1 to 10 (inclusively)

#### Approach one:

A certain user, Ambe, plays the game using the following approach

- Ambe guesses 1 => Too low
- Ambe guesses 2 => Too low
- Ambe guesses 3 => Too low
- Ambe guesses 4 => Too low
- Ambe guesses 5 => Too low
...Util Ambe guesses 10 => Correct

#### Approach two:

Another user, Lum, plays the game using the following approach

- Lum guesses 5 => Too low
- Lum guesses 8 => Too low
- Lum guesses 9 => Too low
- Lum says 10 => Correct

This time around Ambe takes 10 tries to get the answer while Lum takes 4 tries, begining to feel like Lum has a better approach.

What if in another round the the range was 1 to 100 and the correct answer was 5? Can you guess how many steps Ambe and Lum would take?

- Ambe : Would guess a 5 times...
- Lum : Would guess 7 times to get the correct answer

Also consider a round where the range was 1 to 100 and the correct answer was 100? Can you guess how many steps Ambe and Lum would take?

- Ambe : Would guess a 100 times...
- Lum : Would guess 7 times to get the correct answer

When we evaluate both methods used by Lum and Ambe for all the set of rounds passed it becomes clear that Lums solution is better, she took 7 turns to guess 5 and 100, Ambe too 5 turns to guess 5 but 100 turns to guess 100. 

### Analysis : guessing game 

- The game is first defined with clear instructions on what has to be done for someone to win. (The game has a solution or is solvable)
- The range of numbers is provided (The game (problem) is bounded, which is part of what makes it solvable as stated above).
- Characteristically, the game is asking us to "find" or "search" for something hence the any approach used in providing a solution can be called a "searching algorithm"

### Analysis : solutions to guessing game
- Ambe approach (solutuion, alogorithm) seems pretty simple, if you have noticed, he starts guessing from the smallest number and going up until he gets the correct number. We can also say that, he starts guessing from "the start" until he find the correct number. When his guess is wrong he moves to the next and closest guess. This **sequential** method of looking for things is called **Linear searching**. 

- Lums, approach (solutuion, alogorithm) seems pretty much more involved. Lums starts by picking a value at the middle of the range as her guess. If it's greater than the value she is looking for then, all values after that are elimitated leaving her with half the range. If it's less all values before the middle value are also eliminated. Again, leaving her with half the range. This procedure (picking the middle of the range and half conditionally eliminated) is then repeated util she gets the correct guess. Lum's approach only works if the elements in the range are sorted. So incase the elements in the range are not organized then, linear search would be a better solution. This is called **Binary Search**.

### The road home 

Consider the event where a friend has to find your house (or the way to your house) given a few pointers or directions.

The problem : Finding your house
The solution/algorithm : Your pointers and directions (the steps you ask the user to follow)

#### What are the expectation of your algorithm

- Your friend must start somewhere and eventually end at your house. In other words your alogorithm must have a **START** and **AN END**
- Your friend should arrive. If you friend started coming to your house and "kept coming to your house forever" then the algorithm does  not have **AN END** as so it could be said the solution your provided your friend is **INDEFINITE**. In other words a good algorithm description to your house must have a **FINITTE** number of steps, this would also mean that the algorithim is **TIME BOUND**. (If you description has an instruction that leads your friend to moving in cicles then it may be infinite).
- Your friend should be able to reach your house in a reasonable amount of time. In other words, you solution has to be fast. There are several ways to reach your house that could take days, months and or years.
- Your friend must reach your house and not another person's house. In other words the algorithm/description you provided must be **EFFICIENT** or simply **DO THE CORRECT THING** 

This is not an exhaustive list of the things we would expect of a good description or direction to a location but those same things are what would be expected for any "algorithm", we would refer to them later as "characteristics of algorithms"

## Introduction for DSA 

### What is an algorithm?

An algorithm can be defined in multiple ways:

1. An algorithm is a **definitive** solution to a problem
2. An algorithm is a set of steps or instructions that can be followed to solve a problem

### Characteristics of an algorithm

A good algorithm or an algorithm for that matter should posses the following characteristics :

- **Finite** : Must have a begining and an end, with a finite number of steps.
- **Termination** : Must come to an end in a finite amount of time.
- **Correctness/Effectiveness**: Should produce the desired about for a given set of inputs. [Proved using mathematical induction]
- **Efficiency** : Must come to an end in an **acceptable** time limit. (Time & space complexity).
- **Robust**: Produce desirable results in extreme cases. (Edge-cases)
- **Non Ambiguity** : Every statement in the algorithm posses a unique meaning.
- **Reliable** : Should produce thesame results, for the same set of inputs. (Except for random algos)
- Solves a clearly defined problem (guessing a number, finding a house).
- Accepts inputs and must produce a result (for example the guessing game accepts numbers as guesses and returns the result once the correct number is supplied. In the case of the house search the algo should take a specific house location and the result should be "arriving at location") 

## Computability and Complexity of algorithms
When measuring how efficient aglorithms may be, we look at 3 main scenarios:

- Best Case : In the best case evaluation a set of inputs which are extremely easy to solve are provided.
- Worst Case : In the worst case a set of inputs which are extremely hard to solve are provided. 
- Average Case : Measures the perfomance of the algorithm across a range of cases from best, average to worst.

### Growth rate/Order of growth

The rate at which the time to complete or space to execute an algorithm grows as the input/data set grows is called the growth rate or the order of growth. The order of growth is denoted as `O(n)` referred to as **The Big O** notation where `O` represents the order of growth for a dataset of size `n`.

#### The Big O

Is essentially the on-paper definition of the complexity of an algorithm as a function of input-size usually denoted `n`. The `O` comes from "order of magnitude of complexity".

The measure of complexity is relative and not absolute, when we calcute the perfomance or `O(n)` for an algorithm we are doing so relative to other algorithms and not "all agorithms" hence Big O is useful when comparing amongts algorithms that solve the same problem.

NB : Big O, usually **measures the worst case** scenario and so also known as the **upper bound**.

#### Constant runtime operations `O(1)`

Constant time operations take the same amount of time to complete irrespective of the input. For example in Lum's Binary search, every time a middle is picked it has to be compared with the actual correct number. Such an operation takes thesame amount of time irrespective of the number found. `O(1)` is the best possible runtime.

#### Logarithmic runtime operations `O(log n)`

The complexity of logarithm time operations increases lineary as the input size n, increases exponentially. For example in binary search (Lum' method) everytime the number of inputs doubled, the number of guesses only increased by a few units. For 10 elements 4 guesses needs to be made => `(4, 10)`, for 100 elements, it takes 7 steps => `(7, 100)` and for 1000 elements is 10 guesses => `(10, 1000)`.

Logarithmic runtime operations or algorithms are also known as sub-linear time operations.

#### Linear runtime operations `O(n)` 

Linear time operations take an amount of time which is equal to the size of the input in the worst case scenario. So if there's an input of 1000 steps in the worst case, the algorithm would take 1000 units of time. 

*Note that, in the example above, Linear search is better up till a certain value than Binary search, because Binary search involces sorting and each sorting algorithm come with it's own time-space complexity*

### Quadratic runtime operations `O(n^2)`

Quadractic runtime operations would carry out `n^2` operations and so as a function of the size, it takes time which is the input size squared.

#### Quasilinear runtime operations `O(nlog n)`

Quasilinear runtime operations have runtime `O(n)*O(log n) = O(nlog n)`, it's better than quadratic runtime algorithms and worst than linear runtime algorithms. This is common in algorithms that involve steps that own thier own have significant complexities. 

*For example in merge sort (which shall be covered below), there is a binary-search like split operation with time complexity `O(log n)` and we carryout out `n` comparison operations with complexity `O(n)`.*

#### Polynomial & Exponential runtime operations `O(x^n)`

Polynomial runtime operations take complexities in the form `O(f(n^k))` where `f(n^k)` is simply a function of `n` raised to some power `k`. For example `O(log n)` => f = log, n = n, k = 1. Exponential algorithms have time complexities which are powers of the input size, `O(x^n)`. Exponential algorithms are usually considered impractical in the application of solving real-life problems. 

However, **brute-force** algorithms usually have exponential runtimes. 

*ALSO : We also have factorial and or combinatorial runtimes as seen in the case of `Travel-salesman` kind of problems`*

## Credits

- Notes from high school, Thanks to Ngala Ferdinand (Highschool csc teacher)
- https://www.youtube.com/watch?v=8hly31xKli0 (Freecodecamp & treehouse)

