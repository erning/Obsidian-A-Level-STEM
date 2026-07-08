---
title: Artificial Intelligence Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/18 Artificial Intelligence/00 Overview|Artificial Intelligence]]"
status: active
tags:
  - computerscience/advanced
  - solutions
---

# Artificial Intelligence Key Practice Solutions

These solutions correspond to [[30 Computer Science/01 Topics/18 Artificial Intelligence/30 Key Practice Problems|Key Practice Problems]]. The reasoning is the point: read the justification against the alternatives, not just the final answer.

## A. Graphs and search

### Problem 1

A graph is a structure of **nodes** (also called vertices), **edges** (also called links or arcs), and **weights**. In a map-routing problem:

- Nodes are the places - towns, junctions, or addresses. A node stands for a location.
- Edges are the roads connecting them. An edge says "you can travel directly between these two nodes".
- Weights are the cost of using that edge - the distance, time, or fuel. For example, the edge A-B with weight 10 means the road from A to B is 10 km.

A search of the graph then finds the path from a start node to a goal node with the lowest total weight.

### Problem 2

A graph is useful because it turns a problem into a search over a clear structure: the legal moves are the edges, the situations are the nodes, and the cost is the weight, so "find the best solution" becomes "find the best path". Two other uses:

- **State-space search** - each node is a state of the problem (a board position in a game, an arrangement of a puzzle), each edge is a legal move, and the search looks for a path from the start state to a goal state.
- **Planning and decision-making** - nodes are situations an agent could be in, edges are actions, and weights are the cost or effort of each action.

### Problem 3

```text
        10
   A -------- B
   |  \       | \
  4|   \5     |  \6
   |    \     |   \
   C ----D----C    D
       2       2
        \       \
         \7      \7
          E       E
```

A cleaner edge list:

```text
A-B 10   A-C 4   B-C 5   B-D 6   C-D 2   D-E 7
```

The weights represent the cost of travel along each road - here, distance in km. Since the graph is undirected, each edge can be travelled in either direction at the same cost.

### Problem 4

Run Dijkstra from A. Start distance 0; all others infinity. A bracketed value means finalised.

| Step | Finalised node | Frontier (node: tentative dist) | Notes |
|---|---|---|---|
| 0 | - | A:0 | All others infinity |
| 1 | A (0) | C:4, B:10 | Relax A's neighbours; C is smallest |
| 2 | C (4) | B:9, D:6 | A->C->B = 4+5 = 9 beats 10; A->C->D = 4+2 = 6 |
| 3 | D (6) | B:9, E:13 | A->C->D->E = 6+7 = 13; D->B would be 6+6 = 12, worse than 9 |
| 4 | B (9) | E:13 | B's neighbours D and C already finalised |
| 5 | E (13) | - | Goal finalised - stop |

Finalisation order: A, C, D, B, E. Shortest distance A -> E is **13**.

### Problem 5

The shortest path from A to B is **A -> C -> B** with distance **9**, not the direct edge A-B of 10. The path is read from the finalised table by following the back-pointers from B: B was last updated from C (giving 9), and C was updated from A (giving 4), so the path is A -> C -> B. This shows why the direct edge is not always the best route - going through C is cheaper.

### Problem 6

Dijkstra's algorithm guarantees the **shortest path** from the start node to every other node, provided all weights are non-negative. A finalised node never needs revision because it is only finalised when it has the smallest tentative distance on the frontier. Since all remaining edge weights are non-negative, any later path to it would have to add a non-negative cost, so it cannot beat the value already locked in. That is what makes Dijkstra optimal.

### Problem 7

- **g** is the exact cost from the start node to the current node (as in Dijkstra).
- **h** is the heuristic estimate of the remaining cost from the current node to the goal.
- **f = g + h** is the estimated total cost of a path through this node, and A\* selects the frontier node with the smallest f.

For A\* to remain optimal, h must be **admissible** - it must never overestimate the true remaining cost. For a road map, the straight-line "as the crow flies" distance to the destination is admissible, because the shortest road route can never be shorter than the straight line.

### Problem 8

Recommend **A\***. Only one destination matters, and a reliable admissible heuristic (straight-line distance) is available, so A\* explores fewer nodes by being pulled toward the goal while still returning the optimal path. Dijkstra would explore equally in all directions and compute shortest paths to many nodes that are not on the way to the customer, which is wasted work. Dijkstra would be preferred only if shortest paths to many destinations were needed at once, or if no trustworthy heuristic existed.

## B. Neural networks

### Problem 9

```text
Input      Hidden      Output
layer      layer       layer

(x1) ----\
          \-->(h1)--\
(x2) ----/          \-->(y)
          \-->(h2)--/
(x3) ----/    ...
```

The left column is the input layer (one neuron per input value), the middle is the hidden layer(s) that transform the data, and the right is the output layer that produces the answer - a class, a value, or a decision.

### Problem 10

A **weight** is a number on a connection between two neurons that sets how strongly the first neuron's output influences the second. Each neuron sums its weighted inputs, adds a bias, and passes the result through an **activation function** (such as sigmoid or ReLU) that decides the neuron's output. The two are distinct: the weights scale the inputs; the activation function decides the neuron's output from the scaled sum.

### Problem 11

Many hard tasks - recognising an image, understanding speech, translating text - are too complex for a programmer to specify the rules by hand. A neural network instead discovers the rules itself by tuning thousands or millions of weights against examples: given many inputs with their correct outputs, training adjusts the weights a little at a time until the network's outputs match the examples. Because the rules are learned from data rather than hand-coded, the network can solve problems whose explicit rules no human could write down, which is what made machine learning practical on these tasks.

## C. Learning methods

### Problem 12

- **Machine Learning (ML)** - systems that learn patterns from data instead of following fixed rules. The learning signal is training data.
- **Deep Learning (DL)** - ML that uses deep ANNs with many hidden layers. The learning signal is training data, like ML, but the deep structure lets it learn hierarchical features.
- **Reinforcement Learning (RL)** - an agent learns by acting in an environment and receiving rewards or penalties. The learning signal is a reward, not labelled examples.

They relate as follows: **DL is a subset of ML** - every deep-learning system is a machine-learning system that uses a deep neural network. **RL is a separate learning signal**: instead of a fixed dataset of correct answers, the agent explores and learns from the rewards its actions earn. An RL agent may contain a neural network (as in Deep RL), but its learning comes from reward, not from labelled examples.

### Problem 13

(a) **ML**. The emails are labelled ("spam" or "not spam") and the task is to map each email to a class, which is what ML does. DL is unnecessary because the features are structured text data; RL is wrong because labelled examples exist, not a reward signal.

(b) **DL**. Translation from large parallel corpora involves rich hierarchical structure in language that needs many hidden layers to learn. Plain ML struggles to hand-craft features for language; RL is wrong because there are correct target translations, not a sequence of actions and rewards.

(c) **RL**. Chess is a sequence of moves with no single "right answer" per move, but the agent receives a reward (win) or penalty (lose) at the end. RL learns by acting in the environment and maximising reward. ML/DL would need labelled examples of the correct move at every position, which are unavailable.

### Problem 14

RL is chosen when the task is a sequence of decisions with no single correct answer per step, and where learning must happen by trial and error - for example, controlling a robot or playing a game. The learning signal for RL is a **reward** (or penalty) from the environment; the learning signal for supervised learning is **labelled examples**, each with its correct answer.

### Problem 15

(a) **Supervised**. Each house comes with its known selling price, so the data is labelled and the system learns a mapping from inputs to a known output. It produces a regression model that predicts the price of a new house.

(b) **Unsupervised**. The browsing logs have no labels, so the system must discover hidden structure on its own. It produces clusters - groups of similar customers - which could be used for targeted marketing.

### Problem 16

The single deciding fact is whether the data is **labelled**. If each example comes with its correct answer, it is supervised; if only the inputs exist and the system must ask "what groups together?", it is unsupervised. Evaluation is harder for unsupervised learning because there is no "right answer" to compare predictions against - the quality of a clustering is judged indirectly, for example by whether the groups are useful, rather than by an error rate against known labels.

## D. Back propagation and regression

### Problem 17

Back propagation of errors ("backprop") adjusts a neural network's weights during supervised training by working backwards from the output error. The steps, in order:

1. **Forward pass** - feed a training example through the network and record the output it actually produced.
2. **Compute the error** - compare the actual output with the target output using an error function (for example, the difference or the squared error).
3. **Propagate the error backwards** - move from the output layer back through the hidden layers, working out how much each weight contributed to the error.
4. **Adjust the weights** - change each weight by a small amount in the direction that reduces the error.

The steps repeat over many examples until the network's errors are small enough. The **learning rate** controls how large each weight change is: too small and learning is slow, too large and the weights may overshoot and fail to settle.

### Problem 18

Back propagation works backwards from the error because, once the output error is known, the algorithm moves from the output layer back through the hidden layers assigning blame for that error to each weight, then nudges the weights so that next time the same input produces an output closer to the target. The step that computes the comparison between actual and target output is step 2, the **compute the error** step, which uses an error function to compare the network's actual output with the target.

### Problem 19

Regression in machine learning means **predicting a continuous value** - a number on a scale - rather than a category. This contrasts with **classification**, which predicts a discrete label. Examples:

- Regression: predicting a house's price from its floor area (price is a continuous number).
- Classification: deciding whether an email is spam or not spam (the answer is one of two categories).

### Problem 20

The equation of simple linear regression is

$$
y = mx + c
$$

To fit the line, the total error between each real data point and the line is minimised - often the **sum of squared differences** between the predicted y and the actual y. Once learned, the line can predict y for any new x, for example predicting a student's exam score from the hours they studied, or a house's price from its floor area.
