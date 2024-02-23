# Lesson 18

**Analogical reasoning** involves understanding new problems in terms of a family of problems and transferring knowledge of relationships from known problems across domains. We will cover the following:

1. Similarity and case-based reasoning
2. Process of analogical reasoning
3. Design by analogy

## Need For Cross-domain Analogy

Cross domain connections allow an agent to solve new problems based on existing knowledge in some domain. An agent will do this by abstracting out relationships between concepts from one domain to another. These relationships are important because they are the knowledge that is transferred from the source case to the target problem.

## Spectrum Of Similarity

Shown below is table for spectrum of similarity between different KBAI methods from more similar with recording cases to less similar with analogical reasoning:

| Method               | Relations | Objects | Features | Values |
| -------------------- | --------- | ------- | -------- | ------ |
| Recording Cases      | S         | S       | S        | S      |
| Case-based Reasoning | S         | S       | S        | D      |
| Case-based Reasoning | S         | S       | D        | D      |
| Analogical Reasoning | S         | D       | D        | D      |

Where _S_ is for similar and _D_ is for dissimilar

## Process Of Analogical Reasoning

Analogical reasoning consists of five different phases which are usually not linear:

1. Retrieval
2. Mapping
3. Transfer
4. Evaluation
5. Storage

This is just one of the many models on analogical reasoning. Recall that case-based reasoning had the following steps:

1. Retrieval
2. Adaptation
3. Evaluation
4. Storage

Therefore, one of the main differences for analogical reasoning lies within the mapping step where an agent must determine the mapping between relations, objects, features, and values from the source case to the target problem. Once those mappings are determined then knowledge transfer of abstracted relationships from one domain to another can occur.

## Three Types Of Similarity

There are various types of similarity:

1. **Semantic**: conceptual similarity between the target problem an the source case
2. **Pragmatic**: similarity of external factors such as goals
3. **Structural**: similarity between representation structures

## Analogical Mapping

The key for analogical mapping is to look at deep relationships between concepts within a domain rather than looking for superficial relationships. By examining higher order relationships in the source case would allow an agent to map those relationships to the target problem.

## Analogical Transfer

Once an agent understand the mapping between the source case and the target problem the agent could also apply the solution from the source case to the target problem though a strategy transfer. Through this transfer an agent applies abstracted patterns from the source case to the target problem.

## Advanced And Open Issues In Analogy

There are several of advanced topics which have open issues in AI analogy:

- Common vocabulary
- Abstraction and transformation
- Compound and compositional analogies
- Visuospatial analogies
- Conceptual combination

## Section Quizzes

### Similarity Ratings Quiz

> A woman is climbing a ladder

_Which of the situations below is most similar to the situation above_?

1. 2
2. 3
3. 6
4. 4
5. 7
6. 1
7. 5

### Analogical Retrieval I Quiz

> A woman is climbing a ladder

_Mark whether each situation has deep similarity, superficial similarity, both, or neither with the situation above_.

1. Deep and superficial
2. Deep
3. Superficial
4. Deep
5. Neither
6. Deep and superficial
7. Deep

### Analogical Retrieval II Quiz

_What are the deep similarities between these two models (given)_?

- Something revolves around something else
- A force exists between two objects
- Two objects attract each other

### Analogical Mapping Quiz

_How would you map the solar system to the atomic structure_?

- Sun would map to a nucleus
- Planet would map to an electron

### Analogical Transfer Quiz

_What would be transferred into the atomic structure model_?

- Nucleus has mass
- Electron has mass
- Nucleus's mass greater than electron's mass

### Final Quiz

_What did you learn in this lesson_?

- Cross domain analogy is needed in order for an agent to understand a problem in terms of a family of problems and transfer abstract relationship knowledge from one domain to another
- There are many types of relationships on different levels, we think about relationships between objects, features, and values to be on the superficial level whereas relationships of relationships are on a deeper level
- Deep relationships allow an agent to correctly retrieve and map a source case to a target problem such that a strategy could be applied to the target problem
- Analogy is often thought to be a core process of cognition
