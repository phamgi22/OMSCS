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
- return the case with shortest distance d

What about case which multiple dimension?
- return the smallest sum of each dimension distance d
- example: smallest (distance from origin + distance from destination)

## Learning by Recording Cases Connection with Human Cognition
- Memory is important in Learning by Recording cases
- Memory supply answer and lessen the burden on reasoning
