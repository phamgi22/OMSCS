# Lesson 8

In this lesson we will look into _learning by recording cases_. This is one of the fundamental elements of KBAI and also the first topic in analogical reasoning. We will cover the following:

1. Learning by recording cases
2. Nearest neighbor method
3. k-Nearest Neighbor
4. Cases in the real world
   
## What is special about learning by recording cases?
- Learning by recording cases is a core process of cognition
  
## Learning By Recording Cases

A **case** is an encapsulation of a past experience. The process for learning by recording cases is as follows:

1. Given a new problem `a`
2. Retrieve most similar prior problem `b` from memory
3. Apply problem `b` solution to problem `a`

Example:
- debugging similar code issue
- tying shoe laces
- doctor making diagnosis

## Nearest Neighbor In k-Dimensional Space

Sometimes plotting objects on a two dimensional grid does not outright reveal a clear answer. In this case we use the k-Nearest Neighbor method which utilizes all neighbors to find the nearest distance (most similar) between all neighbors.
- Use euclidian distance to find the nearest distance:
- existing case: A(xc, yc)
- list of seen cases: B1 B2 B3 B4
- a seen case example: B1 (xn, yn)
- euclidian distance d = square root of {(yc - yn)^2 + (xc - xn)^2}

## Section Quizzes

### Retrieval By Nearest Neighbor Quiz

_What color is this block (provided)_?

Red, based on the provided diagram.

### Recording Cases In Real Life Quiz

_What route is most similar to this new problem (provided)_? D.

### Final Quiz

_What did you learn in this lesson_?

- Cases are encapsulations of past experiences
- Our interactions with the world have certain patterns of regularity so we can use solve our current problems with problems we have previously encountered in the past
- The cognitive architecture includes reasoning, memory and learning; by learning with cases we can utilize the memory aspect of cognition
