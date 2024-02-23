# Lesson 6

We will discuss **production systems** in this lesson. Production systems are a kind of cognitive architecture in which knowledge is represented in the form of rules. This is the last topic under the fundamental topics. We will also cover the following:

- Cognitive architectures
- Production systems
- Chunking

## Function Of A Cognitive Architecture

A **cognitive agent** is a function that maps a perceptual history into an action.

## Levels Of Cognitive Architecture

There are various levels of cognitive architecture:

- Low: hardware/implementation level (e.g., brain, transistor)
- Medium: algorithm/symbol level (e.g., means-ends analysis, semantic networks)
- High: task/knowledge level (e.g., selecting a pitch, playing baseball)

The lower levels provide an _architecture_ for higher levels and the higher levels provide _content_ for lower levels.

## Assumptions Of Cognitive Architectures

There are several of assumptions for cognitive architectures:

1. Goal-oriented: take action to achieve goal
2. Rich, complex environment
3. Significant knowledge: use knowledge about the world
4. Symbols and abstractions: capture knowledge with symbols
5. Flexible and function of the environment: enviroment change will lead to behavior change
6. Learning: learn from experience, learn from interact with the world

## Architecture, Content, and Behavior

In general, it could be said that `architecture + content = behavior`. Suppose that our architecture is fixed, then the behavior of agents could be directly mapped to the knowledge content.

## A Cognitive Architecture For Production Systems

The **SOAR** architecture is one of the architectures for deliberation (recall the diagram of a cognitive system from the first lesson). SOAR can also cover certain aspects of reaction as well as meta-cognition.

SOAR consists of long-term memory and a **working memory**, where long-term memory contains 3 different kinds of knowledge:

1. **Procedural**: has to do with how to do accomplish certain tasks (e.g., how to cook a specific dish?)
2. **Semantic**: includes generalizations in the form of concepts and models of the world (e.g., how does food get its flavor? how does a plane fly)
3. **Episodic**: includes specific events (e.g., what did you cook last weekend?)

## Baseball example
- Percepts of the world is put inside the working memory:
  - goal
  - score
  - average
  - batter name
- The production rule that decide which action to take to store in procedura knowledge of long term memory
  

## Chunking

Referring to our baseball example, what if we have two rules that the SOAR agent cannot decide on? 
- This mean the agent encounters an impasse
  - because not enough knowledge
  - or two actions are being selected
- SOAR will learn rule to break the impasse
  - SOAR can invoke episodic knowledge to learn a new rule
- **Chunking** is the process of SOAR learning rule that can break the impasse
- Chunking is triggered only when impasse occur
- Impasse tell SOAR what the goal of chunking is

## Fundamentals Of Learning

The theory of reasoning states helps us address questions such as:

1. What to learn?
2. When to learn?
3. Why do we learn?
4. How do we learn?

We start with reasoning first then work backwards to learning. 
This occurred for our production system with the baseball example. 
When the logic was blocked, the system had to refer to its episodic knowledge into order to fulfill the goal.

## Production systems connecition with human cognition
- Production system were proposed to be model of human cognition
  - Working memory == short term memory in human cognition (capacity 7 +/- 2 items)
  - When solving algebra problems, SOAR production systems perform similar to human

