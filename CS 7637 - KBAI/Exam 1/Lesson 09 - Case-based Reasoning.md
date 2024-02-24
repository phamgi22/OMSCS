# Lesson 9

In this lesson we will cover topics on _case-based reasoning_ where cognitive agents address new problems by tweaking solutions to similar previously encountered problems. 
Case-based reasoning builds on top of learning by recording cases
- Learning by recording cases: case in memory is identical to current case
- Case based reasoning: case in memory is similar to current case
  
We will also cover the following:
1. Recording cases revisited
2. Need for case-based reasoning
3. Phases of case-based reasoning
4. Advanced case-based reasoning: new methods of case retrieval

## Recording Cases To Case-based Reasoning

There are several of steps for case-based reasoning:

1. **Retrieval**: retrieving a case from memory similar to the current problem
2. **Adaptation**: adapting the solution to that case to fit the current problem
3. **Evaluation**: evaluating how well the adapted solution addresses the current problem
4. **Storage**: storing the new problem and solution as a case

## Assumptions Of Case-based Reasoning

There are several assumptions for case-based reasoning:

1. Patterns exist in the world
2. Similar problems have similar solutions

## Case Adaptation

There are several ways an agent could use case adaptation to solve a problem:

1. Case adaptation by model of the world: use a previous solution or model to adapt and solve a new problem(knowing how to go from home to office, and office to restaurant, adapt way from home to restaurant)
2. Case adaptation by recursive reasoning: break the new problem into sub-problems then use partial solutions from other problems to solve the new problem
3. Case adaptation by rules: use rules to adapt to a new problem (Example: return home from restaurant by reversing restaurant to home. This does not always works bc for example, not all turn can be reversed)

## Case Evaluation
- Evalute how well the adapted solution addresses the current problem
- There are multiple ways to evaluate possible solutions, one common way is to run a simulation or in terms of programming, run unit or end-to-end tests.
- One way to evaluate is simulation:
  - Example: simulate the return way home from restaurant
  - If evaluation fail: go back to adaptation, might also return to retrival phase to search for a difference problem
- Another way to evaluate is adaptation to another designer for critique
## Case Storage

Once solutions are evaluated for correctness, we could store solutions in multiple ways:

1. Case storage by index(less efficient): storing a solution in such a way that it could be retrieved via index where the index could be some sort of property related to the solution
2. Case storage by discrimination tree: storing a solution in such a way that it could be retrieved via tree structure where each node could have multiple branches

## Advanced Case-based Reasoning

Case-based reasoning does not always have to go from retrieval to storage, it could also do the following:

- Case base reasonging does **NOT** need to be linear
- Evaluation to adaptation: evaluation found, the solution failed; try adapting again
- Evaluation to retrieval: evaluation found, the solution failed; try retrieving a different solution
- Adaptation to retrieval: the retrieved solution could not be adapted; retrieve a different solution
- Retrieval to evaluation: retrieved case perfectly matches the current problem, no adaptation needed
- Can also store failed cases
  
When storing cases, we should only store noteworthy cases, including interesting failed cases. However, we should **not** simply store all successful or failed cases(utility problem).
## Connection with human cognition
- spectrum of similarity
  - low similarity: learn to deal with these cases later in the future
  - mid similarity: tweak case retrieved and apply to new case, adapt as needed
  - high simlarity: apply solution to new case directly, adapt as needed
- learning by recording case shift balance from reasoning to learning and memory, while case based reasoning unify all three

