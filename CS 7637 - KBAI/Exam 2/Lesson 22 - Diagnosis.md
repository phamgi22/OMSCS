# Lesson 22

In this lesson we will cover _diagnosis_ which identifies the faults responsible for a malfunctioning system. We will cover the following:

- Defining diagnosis
- Data and hypothesis spaces
- Mapping data to hypothesis
- Two views of diagnosis

## Defining Diagnosis

**Diagnosis** is to determine what is wrong with a malfunctioning device or what is the fault that causes a device to malfunction.

## Data Space And Hypothesis Space

We can think of diagnosis as a process that maps data from a _data space_ to a _hypothesis space_. In diagnosis the mapping between data from the data space to hypotheses in the hypothesis space is `N * N`. This can be very complicated very quickly.

Consequently, the data space is abstracted such that it could be mapped to an abstract hypothesis (bottom-up classification). Once an abstract hypothesis has been created, the next process is to refine the hypothesis such that the finalized hypothesis will maximize all data available in the data space (top-down classification).

## Problems With Diagnosis As Classification

There are several problems with diagnosis however:

1. One data point may map to multiple hypotheses
2. One hypothesis may map to multiple sets of data
3. Multiple hypothesis may map to multiple sets of data
4. Hypotheses may be mutually exclusive
5. Data points may interact

Point 5 is difficult to account for in practice so it is useful to shift from a sole classification approach to diagnosis to an abduction approach.

## Deduction - Induction - Abduction

Below highlights the steps for deduction, induction, and abduction:

1. **Deduction**: given the rule and the cause, deduce the effect (Modus Pones)
2. **Induction**: given a cause and an effect, induce a rule
3. **Abduction**: given a rule and an effect, abduce a cause (diagnosis)

While deduction is _truth preserving_, induction and abduction are not.

## Criteria For Choosing A Hypothesis

Below are criteria for choosing a hypothesis

1. Hypothesis must cover as much of the data as possible
2. The smallest number of hypothesis ought to be used
3. Some hypotheses may be more likely than others

## Completing The Process

To complete the diagnosis process an agent would need to transfer the hypothesis from the _hypothesis space_ and select the proper treatment (action) in the _treatment space_. Depending on the results of the treatment, the data gained from treatment would be fed into the _data space_ and thus the process begins again.

## Section Quizzes

### Diagnosing Illness Quiz

_What illness (or set of illnesses) would you use to diagnose this patient (given symptoms)_?

Thetadesis: Elevated B, Reduced C, Reduced H

### Diagnosis As Abduction Quiz

_What illness (or set of illnesses) would you use to diagnose this patient (given symptoms)_?

- Betatosis: Elevated B, Reduced C, Elevated E, Reduced H
- Zetad: Elevated B, Reduced C, Reduced E, Reduced F

### Final Quiz

_What did you learn in this lesson_?

- Diagnosis occurs whenever our expectations are violated such that we could determine the cause
- Diagnosis is a task which we could use several methods to address (e.g., case-based reasoning, etc.)
- Diagnosis is a very complicated classification task which may be untangled with the use of deduction, induction, or abduction
