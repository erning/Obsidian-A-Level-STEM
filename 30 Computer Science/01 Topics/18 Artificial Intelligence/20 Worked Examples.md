---
title: Artificial Intelligence Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Artificial Intelligence](00%20Overview.md)"
status: active
tags:
  - computerscience/advanced
  - worked-examples
---

# Artificial Intelligence Worked Examples

These examples model how to reason through scenario-based questions on graphs and search, neural networks, and the learning methods. The aim is not to recite definitions but to show how to model a problem as a graph, trace a search by hand, and choose a learning method for a named situation. Candidates are not required to write graph algorithms, only to understand and use them.

## Source Route

- Syllabus: CAIE Computer Science 9618, A Level section 18 - Artificial Intelligence.
- Assessed in Paper 3.
- Topics: graphs in AI (nodes, edges, weights); Dijkstra and A\* search; artificial neural networks; Machine Learning, Deep Learning, Reinforcement Learning; supervised vs unsupervised learning; back propagation of errors; regression methods.

## Example 1: Model a Delivery Problem as a Graph

**Prompt.** A courier must drive between five towns. The road distances in km are: A-B 10, A-C 4, B-C 5, B-D 6, C-D 2, D-E 7. Explain how to model this as a weighted graph, naming the three structural parts and giving one example of each. Then state what a search of the graph would aim to find.

**Solution.** A graph is a structure of nodes, edges, and weights. For this routing problem:

- **Nodes** are the towns A, B, C, D, E. A node stands for a place or state.
- **Edges** are the roads between them. An edge says "you can travel directly between these two nodes".
- **Weights** are the road distances. The weight is the cost of using that edge - here, km, but it could equally be time or fuel.

ASCII form:

```text
        10
   A -------- B
   |  \       | \
  4|   \5     |  \6
   |    \     |   \
   C --- D    C    D
     2 /        2 /
      /          /
     D          D
      \7        \7
       E        E
```

A cleaner edge list, with weights:

```text
A-B 10   A-C 4   B-C 5   B-D 6   C-D 2   D-E 7
```

A search of this graph aims to find the path from the start node (say A) to a goal node (say E) with the lowest total weight - that is, the shortest route.

**Check.** If the prompt gives distances, times, or costs, those become the weights. If it does not name a cost, the graph is unweighted and search only counts hops.

## Example 2: Trace Dijkstra from A to E

**Prompt.** Using the edge set A-B 10, A-C 4, B-C 5, B-D 6, C-D 2, D-E 7, run Dijkstra's algorithm from A to E. Give the finalisation order and the shortest distance.

**Solution.** Start at A with distance 0; all other tentative distances begin at infinity. A bracketed value means finalised.

| Step | Finalised node | Frontier (node: tentative dist) | Notes |
|---|---|---|---|
| 0 | - | A:0 | All others infinity |
| 1 | A (0) | C:4, B:10 | Relax A's neighbours; C is smallest |
| 2 | C (4) | B:9, D:6 | A->C->B = 4+5 = 9 beats 10; A->C->D = 4+2 = 6 |
| 3 | D (6) | B:9, E:13 | A->C->D->E = 6+7 = 13; D->B would be 6+6 = 12, worse than 9 |
| 4 | B (9) | E:13 | B's neighbours D and C already finalised |
| 5 | E (13) | - | Goal finalised - stop |

Finalisation order: A, C, D, B, E.

Shortest distance A -> E is **13**, along the path read back from E: E <- D <- C <- A, so **A -> C -> D -> E**.

**Check.** Dijkstra always finalises the node with the smallest tentative distance, so the finalisation order goes in increasing distance from A. If you ever finalise a node before its smallest tentative is found, the trace is wrong.

## Example 3: Dijkstra vs A\* for a Single Destination

**Prompt.** A satellite-navigation app must find one route from a driver's current town to a chosen destination on a road map. Compare Dijkstra's algorithm and A\* and recommend one, stating why.

**Solution.**

- Both find shortest paths on graphs with non-negative weights.
- **Dijkstra** selects the frontier node with the smallest distance-so-far `g`. It explores equally in all directions from the start, so it finds shortest paths to *every* node, not just the destination. That is more work than needed when only one destination matters.
- **A\*** selects the frontier node with the smallest `f = g + h`, where `g` is the exact cost from the start and `h` is a heuristic estimate of the remaining cost to the goal. A road map has a natural heuristic: the straight-line "as the crow flies" distance to the destination, which can never exceed the real road distance, so the heuristic is admissible.
- Because `h` pulls the search toward the goal, A\* explores far fewer nodes than Dijkstra while still returning the optimal path, provided `h` never overestimates.

Recommendation: **A\***, because only one destination is needed and a reliable admissible heuristic (straight-line distance) is available, so A\* reaches the goal faster without giving up optimality. Dijkstra would be preferred only if shortest paths to many destinations were needed at once, or if no trustworthy heuristic existed.

**Check.** With `h = 0` everywhere, A\* collapses into Dijkstra. The advantage of A\* comes entirely from a good, admissible heuristic.

## Example 4: ANN Structure and How Learned Weights Enable Learning

**Prompt.** Draw the layers of an artificial neural network (ANN) and explain what a weight does. Then explain why the fact that weights are *learned* made machine learning practical on hard tasks.

**Solution.** An ANN is built from neurons arranged in layers: an input layer, one or more hidden layers, and an output layer.

```text
Input      Hidden      Output
layer      layer       layer

(x1) ----\
          \-->(h1)--\
(x2) ----/          \-->(y)
          \-->(h2)--/
(x3) ----/    ...
```

Each connection between neurons carries a **weight**, a number that sets how strongly one neuron's output influences the next. Each neuron sums its weighted inputs, adds a bias, and passes the result through an activation function that decides its output.

The key point is that the weights are **learned from data**, not hand-programmed. Given many example inputs with their correct outputs, training adjusts every weight a little at a time until the network's outputs match the examples. This matters because many tasks - recognising an image, understanding speech, translating text - are too complex for a programmer to specify the rules by hand. The ANN discovers the rules itself by tuning thousands or millions of weights against examples, which is what made machine learning practical on these hard tasks.

**Check.** Do not confuse the weights with the activation function. Weights scale the inputs; the activation function decides the neuron's output.

## Example 5: Choose Between ML, DL, and RL

**Prompt.** For each situation, choose Machine Learning (ML), Deep Learning (DL), or Reinforcement Learning (RL), and justify it against the others.

(a) A bank wants to flag fraudulent card transactions using a large archive of past transactions, each already marked "fraud" or "not fraud".

(b) A system must transcribe spoken English into text from raw audio.

(c) A robot arm must learn to pick up irregular objects by trial and error.

**Solution.**

(a) **ML** (specifically supervised learning). The data is labelled and the task is to map each transaction to a class, which is exactly what ML does. DL is unnecessary because the features are already structured tabular data; RL is wrong because there are labelled examples, not a reward signal.

(b) **DL**. Raw audio and speech have rich hierarchical structure that needs many hidden layers to learn, which is what a deep neural network provides. Plain ML struggles to hand-craft features for sound; RL is wrong because there is a fixed dataset of correct transcriptions, not a sequence of actions and rewards.

(c) **RL**. Picking up objects is a sequence of actions where no single "right answer" per step exists, but the agent receives rewards (a successful grasp) or penalties (dropping the object). RL learns by acting in an environment and maximising reward, which fits. ML/DL would need labelled examples of the correct move at every instant, which are unavailable here.

**Check.** Place them in a nesting: DL is a subset of ML (a deep network is still a machine-learning model). RL is a separate learning signal - reward, not labelled examples.

## Example 6: Supervised vs Unsupervised for a Dataset

**Prompt.** A retailer has a table of customer purchase records. In scenario X, each record is tagged with the customer's spending bracket. In scenario Y, the records have no tags at all and the retailer wants to group similar customers together. For each scenario, state whether it is supervised or unsupervised learning, give one reason, and name what the system would produce.

**Solution.**

- Scenario X is **supervised**. The records carry labels (the spending bracket), so the system learns a mapping from inputs to known outputs. It would produce a classifier that predicts the spending bracket of a new customer.

- Scenario Y is **unsupervised**. The records have no labels, so the system must discover hidden structure on its own. It would produce clusters - groups of customers with similar purchasing behaviour - which the retailer could use for targeted marketing.

The single deciding fact is whether the data is labelled. If you can say "the correct answer for this record is X", it is supervised; if you only have the data and must ask "what groups together?", it is unsupervised.

**Check.** Supervised produces a classifier or regression model; unsupervised produces clusters or groupings. If the prompt mentions "predict a known value", it is supervised; "find groups" points to unsupervised.

## Example 7: Back Propagation of Errors at a High Level

**Prompt.** Describe the back propagation of errors process in a neural network at a high level, in the correct order. State what the learning rate controls.

**Solution.** Back propagation ("backprop") adjusts the network's weights during supervised training by working backwards from the output error. The steps, in order:

1. **Forward pass** - feed a training example through the network and record the output it actually produced.
2. **Compute the error** - compare the actual output with the target output using an error function (for example, the difference or the squared error).
3. **Propagate the error backwards** - move from the output layer back through the hidden layers, working out how much each weight contributed to the error.
4. **Adjust the weights** - change each weight by a small amount in the direction that reduces the error.

These steps repeat over many examples until the network's errors are small enough. The **learning rate** controls how large each weight change is: too small and learning is slow, too large and the weights may overshoot and fail to settle.

The intuition: backprop assigns blame for the output error to each weight, then nudges the weights so that next time the same input produces an output closer to the target. No code is required by the syllabus, only this understanding.

**Check.** The order is forward, error, backward, adjust. A common mistake is to describe it as adjusting weights to "increase accuracy" without mentioning it works backwards from the error.

## Example 8: Regression in Machine Learning

**Prompt.** Explain what regression means in machine learning and how it differs from classification. Give the equation of simple linear regression and state what is minimised to fit it.

**Solution.** Regression in machine learning means **predicting a continuous value** - a number on a scale - rather than a category. This contrasts with classification, which predicts a discrete label.

The simplest form is **linear regression**: fit a straight line through the data points so that the line best predicts the output value from the input. Given a set of input-output pairs, the line

$$
y = mx + c
$$

is chosen to minimise the total error between each real point and the line, often the sum of squared differences. Once learned, the line can predict y for any new x - for example, predicting a house's price from its floor area, or a student's exam score from hours studied.

More complex regression (polynomial, multi-variable) fits curves or surfaces, but the idea is the same: learn a function from inputs to a continuous output by minimising prediction error on the training data.

**Check.** If the output is a number on a continuous scale, it is regression; if the output is a category or class, it is classification. Calling regression "classification" is the common trap.
