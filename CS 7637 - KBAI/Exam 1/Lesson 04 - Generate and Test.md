# Lesson 4

In this lesson we will be covering the following topics:

- Generate and test method
- Smart generators
- Smart testers
- Generate and test for Raven's Progressive Matrices

## Why we need generator and tester ?
- Because AI agent have limited ability, can only produce plausible solution and then tester test for the desire solution
- If AI agent have all the knowledge of the world and limitless ability, then the generator can generator THE optimal solution
  
## Guards And Prisoners

KBAI is a collection of three things:

1. Knowledge representations
2. Problem solving techniques
3. Architectures

Referring back to the guards and prisoners problem, a typical _dumb_ generator will generate all possible scenarios and a _dumb_ tester will eliminate scenarios based on specific rules.

## Dumb generator and dumb tester
- Generator generates too many unproductive states leading to combinatorial explosion
- Tester does not prune away unproductive states
  
## Smart Testers

A smart tester will not only remove scenarios based on rules, it will also check for identical states.

## Smart Generators

A smart generator will not generate all possible scenarios, instead it will generate states which are not redundant or illegal.

## Generate and test connection with human congition
Human genetic combination is also a generate and test process with evolution
