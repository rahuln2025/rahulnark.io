---
title: 'Basics of Probability'
date: 2026-04-06
permalink: /posts/2026/04/blog-post-1/
tags:
  - probability
  - statistics
  - basics
---

# Basics of Probability

For those transitioning to mathematics / machine learning from other fields, sometimes the symbols and terminologies in statistics seem intuitive but lack rigour and confidence. These basics concepts will add confidence when reading mathematical texts and research papers dealing with probabilities. 

This summary of concepts comes from the lectures on 'Stochastic Methods for Material Science' conducted by Jun.-Prof. Björn Sprungk at the TU Bergakademie Freiberg, where I built my first basics of probability. 

## Basic terminologies / concepts

### Randomness
**Random experiment** is:
- well-defined, repeatable,
- has a known set of possible outcomes $\Omega$,
- but actual outcome (result) of a single execution of the expt. is known,

Here, $\Omega$ is the sample space, i.e. the set of all possible outcomes. 

**An Event** is a set of single outcomes $A \subseteq \Omega$. E.g. in rolling the dice, the cases when number of dots is even forms is a subset of all possible outcomes of a dice roll and hence an event. 

Set operations/properties for events: 
- $A \cup B$: $A$ **or** $B$, Union
- $A \cap B$: $A$ **and** $B$, Intersection
- $A \subseteq B$: $A$ is a subset of $B$, i.e. $B$ includes all outcomes in $A$. 
- if $A \cap B = \emptyset$, then $A$ and $B$ are **exclusive**.

### Probability

#### Basic intuition 

Probability is defined for an event $A \subseteq \Omega$ of a random experiment as:

the limit of event $A$'s relative frequency if the experiment is repeated infinitly many times: 

$$ P(A) = \displaystyle \lim_{n \to \infty} \frac{\text{number of times A occured in $n$ repetitions}}{n}$$

#### Formally (Probability as a function) 

Probability $P$ is a *function* that maps events $A \subseteq \Omega$ a number in $[0, 1]$ such that:
- $P(\Omega) = 1$ for the sample space (certain and known) always holds, 
- For mututally exclusive events $A_i \cap A_j = \emptyset$ for $ i \neq j$,

$$ P(A_1 \cup A_2 \cup A_3 \cup ...) = P(A_1) + P(A_2) + P(A_3) + ...$$

$P(A)$ is called probability of the event $A$. 

I personally prefer the 'probability as a function' definition coming from more of a deterministic math background, where functions explain a variety of things. 

#### Properties of probability (function)

- $P(A^c) = 1 - P(A)$
- $P(\emptyset) = 0$ *(impossible event)*
- $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ *(additivity, easily understood as Venn diagrams)*
    - special case if $A$ and $B$ are exclusive: $P(A \cup B) = P(A) + P(B)$
- if $A \subseteq B \implies P(A) \leq P(B)$ *(monotonicity, larger event set has higher probability)*

#### Conditional Probability, and allied results

For two events $A$ and $B$, the **conditional probability of $A$, given $B$** is defined as:

$$P(A \mid B) = \frac{P(A \cap B)}{P(B)} $$

provided $P(B) > 0$. 

**Bayes' theorem**: For two events $A$ and $B$ with $P(B) > 0$, the following equation holds: 
$$
P(A \mid B) = \frac{P(B \mid A) \cdot P(A)}{P(B)}
$$

**Total law of probability**: Given two events $A$ and $B$ with $P(A) > 0$ and $P(B) > 0$, the following holds: 

$$
P(B) = P(B \mid A)\cdot P(A) + P(B \mid A^c)\cdot P(A^c) 
$$

This law is useful in cases where conditional probabilities $P(B \mid A)$ and $P(B \mid A^c)$ are easier to determine as compared to $P(A \cap B)$. 

**Independent events**: $A$ and $B$ are independent iff $P(A\cap B) = P(A) \cdot P(B)$. 

For a finite set $A_1, A_2, A_3, ..., A_n$ of events, they are **mututally independent** iff for every $k \leq n$ and every choice of $A_{i_1}, ..., A_{i_k}$ of $k$ events from $A_1, A_2, A_3, ..., A_n$, 

$$
P(A_{i_1} \cap ... \cap A_{i_k}) = P(A_{i_1}) \cdot ... \cdot P(A_{i_k}).
$$


### Random Variables, CDF, PMF (real stuff starts here...)

Things from here on may seem more rigorous and abstract, but let's try to keep the base intuition in mind and follow these terminologies: 

#### Random Variable

**Intuition**: A (real-valued) random variable $X$ is a variable whose values are random.

**Mathematically**: 

A random variable is a mapping $X : \Omega \rightarrow \mathbb R$. 

**A random variable X assigns to each outcome of a random experiment a real number**. 

An actual outcome $x = X(\omega) \in \mathbb R, \omega \in \Omega$, of a random variable $X$ is called a **realization of $X$**. 

**Simple understanding:**

 - A random variable $X$ is a **function** that maps from $\Omega$ (sample space) to $\mathbb{R}$ (set of real numbers).
- For each outcome $\omega \in \Omega$, the random variable assigns a real number $X(\omega) = x \in \mathbb{R}$.  
- When we observe a specific outcome from an experiment, we get a **realization** $x$ of the random variable $X$.
- **Capital letter** $X$ denotes the random variable (the function), **lowercase** $x$ denotes a specific realization (a number).




To be continued...