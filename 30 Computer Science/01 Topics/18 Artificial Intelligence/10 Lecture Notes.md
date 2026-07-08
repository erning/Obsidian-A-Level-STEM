---
title: Artificial Intelligence Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/18 Artificial Intelligence/00 Overview|Artificial Intelligence]]"
status: active
tags:
  - computerscience/advanced
  - lecture-notes
---

# Artificial Intelligence Lecture Notes

This A Level topic is the technical foundation behind the AI whose impact and
applications you met in AS section 7 (Ethics and Ownership). Where that earlier
topic asked what AI *does* to society, this one asks how the methods actually
work: how a problem is modelled as a graph and searched with Dijkstra or A\*,
and how systems learn from data through neural networks, machine learning, deep
learning and reinforcement learning.

## Source Route

This note follows CAIE Computer Science 9618, A Level section 18:

- 18.1 Artificial Intelligence

Section 18 is examined in Paper 3. Candidates are **not** required to write
algorithms that set up, access, or search a graph - only to understand and use
them.

## 1. Graphs in AI: purpose and structure

A **graph** is a structure of **nodes** (also called **vertices**) connected by
**edges** (also called **links** or **arcs**). Each edge may carry a **weight**,
a number that stands for the cost of using that connection - distance, time,
fuel, difficulty, anything you want to minimise. In AI the graph is a way of
modelling a problem so that solving it becomes a matter of searching the graph
for a good path.

Two classic uses:

- **Map routing** - nodes are places, weighted edges are the roads between them;
  the search finds the shortest or cheapest route.
- **State-space search** - each node is a state of the problem (a board
  position in a game, an arrangement of a puzzle), each edge is a legal move,
  and the search looks for a path from the start state to a goal state.

A small weighted graph:

```text
          4
    A ---------- B
    | \          | \
   2|  \3        |  \1
    |   \        |   \
    C    D ----- E    F
     \3 |  \2   |1 /
      \ |   \   | /
       G ---- H
          5
```

Nodes: A, B, C, D, E, F, G, H. An edge such as `A--4--B` means "you can travel
between A and B at cost 4". The search problem is: starting at some node (say
A), find the best path to a target node (say H). "Best" usually means lowest
total weight.

Graphs can be **directed** (edges run one way) or **undirected** (edges run both
ways, like the map above). The structure is the same; only the direction of
travel differs.

## 2. Search algorithms: Dijkstra and A\*

Both Dijkstra's algorithm and A\* find a path through a weighted graph from a
start node to a goal node. They share the idea of a **frontier** of nodes whose
best-known cost is not yet final, and a table of **tentative distances** from
the start to every node reached so far.

### Dijkstra's algorithm

**Dijkstra's algorithm** guarantees the **shortest path** from the start node to
every other node (with non-negative weights). It works by repeatedly taking the
frontier node with the smallest tentative distance, marking it **final**, and
then using it to relax (improve) the tentative distances of its neighbours.

High-level steps:

1. Set the start node's distance to 0, all others to infinity. Place the start
   on the frontier.
2. Pick the frontier node with the **smallest** tentative distance. This is now
   **final** - its shortest distance is locked in.
3. For each neighbour of the finalised node, compute "distance so far + edge
   weight". If this beats the neighbour's stored tentative distance, update it
   and note the path back through the finalised node.
4. Repeat steps 2-3 until the goal is finalised (or every reachable node is
   finalised).
5. Read off the path by following the recorded back-pointers from goal to
   start, then reversing.

Because each node is finalised only at its true minimum, Dijkstra never has to
revise a finalised value - it is **optimal**.

### Worked trace of Dijkstra

Find the shortest path A → H on the graph in section 1. Edge weights: A-B 4,
A-C 2, A-D 3, B-F 1, B-E (via the layout, take B-E as 4 - see note), D-E 2,
E-H 1, C-G 3, D-G (none), G-H 5. To keep the trace clean, use this definite
edge set:

```text
A-B 4   A-C 2   A-D 3   C-D 1   D-E 2   E-H 1   C-G 4   G-H 3
```

Start at A, goal H. Tentative distances shown as the frontier evolves. A
bracketed value means finalised.

| Step | Finalised node | Frontier (node: tentative dist) | Notes |
|---|---|---|---|
| 0 | - | A:0 | All others ∞ |
| 1 | A (0) | B:4, C:2, D:3 | Smallest is C |
| 2 | C (2) | D:3, B:4, G:6 | A→C→D = 3 ties A→D = 3, keep 3 |
| 3 | D (3) | B:4, E:5, G:6 | A→C→D→E = 2+1+2 = 5 |
| 4 | B (4) | E:5, G:6 | B's only other neighbour already worse |
| 5 | E (5) | H:6, G:6 | E→H gives 5+1 = 6 |
| 6 | H (6) | G:6 | Goal finalised - stop |

Shortest distance A → H is **6**. The path, read back from H: H ← E ← D ← C ← A,
so **A → C → D → E → H**.

### A\* algorithm

**A\*** (A-star) finds a path to a **single goal** faster by adding a
**heuristic** - an estimate of the remaining cost from each node to the goal.
Instead of choosing the frontier node with the smallest distance-so-far, it
chooses the one with the smallest `f = g + h`, where:

- **g** is the exact cost from the start to this node (as in Dijkstra),
- **h** is the heuristic estimate of the remaining cost to the goal.

If the heuristic **never overestimates** the true remaining cost (it is
*admissible*), A\* still finds the optimal path, but it explores far fewer nodes
because it is pulled toward the goal rather than spreading evenly in all
directions. A road-map example of h is the straight-line distance "as the crow
flies" to the destination, which can never exceed the real road distance.

### Comparison

| Aspect | Dijkstra | A\* |
|---|---|---|
| Selection rule | Smallest tentative distance `g` | Smallest `f = g + h` |
| Uses a heuristic? | No | Yes |
| Explores | Equally in all directions | Pulled toward the goal |
| Nodes explored | Many (broad) | Fewer (focused), if h is good |
| Guarantees shortest path? | Always (non-negative weights) | Yes, if h is admissible (never overestimates) |
| Best for | Shortest paths to *all* nodes; no goal estimate available | A path to *one* goal; a good heuristic is available |

The trade-off: A\* is only as good as its heuristic. With `h = 0` everywhere it
collapses back into Dijkstra.

## 3. Artificial neural networks

An **artificial neural network (ANN)** is a model loosely inspired by the brain.
It is built from **neurons** (also called nodes or units) arranged in layers:

- An **input layer** that receives the data (one input value per neuron).
- One or more **hidden layers** that transform the data.
- An **output layer** that produces the answer (a class, a value, a decision).

Each connection between neurons carries a **weight** - a number that sets how
strongly one neuron's output influences the next. Each neuron sums its weighted
inputs, adds a **bias**, and passes the result through an **activation
function** (such as a step, sigmoid, or ReLU) that decides its output.

```text
Input     Hidden      Output
 layer     layer(s)    layer

 (x1) ----\
           \-->(h1)--\
 (x2) ----/--        \-->(y)
           \-->(h2)--/
 (x3) ----/    ...   /
```

The key idea is that **the weights are learned from data** rather than
hand-programmed. Given many example inputs and the correct outputs, a training
process adjusts every weight a little at a time until the network's outputs
match the examples. This is what made **machine learning** practical on hard
tasks (image recognition, speech, translation) where writing explicit rules is
impossible: the ANN discovers the rules itself by tuning thousands or millions
of weights.

## 4. Machine Learning, Deep Learning, Reinforcement Learning

These three terms describe how a system improves, and they nest and overlap.

| Method | What it is | Learning signal | Why use it | Typical use |
|---|---|---|---|---|
| **Machine Learning (ML)** | Systems that learn patterns from data instead of following fixed rules | Training data (examples) | Tasks too complex to hand-code; patterns hidden in large data | Spam filtering, price prediction, recommendation |
| **Deep Learning (DL)** | ML that uses **deep** ANNs - many hidden layers | Training data, like ML | Tasks with rich structure (images, sound, language) that need many layers to learn hierarchical features | Image recognition, machine translation, speech-to-text |
| **Reinforcement Learning (RL)** | An **agent** learns by acting in an **environment** and receiving **rewards** or **penalties** | A reward signal (not labelled examples) | Sequential decisions where there is no single "right answer" per step; learn by trial and error | Game playing (chess, Go), robotics, navigation, control |

How they relate:

- **DL is a subset of ML** - every deep-learning system is a machine-learning
  system that happens to use a deep neural network.
- **RL is a different learning signal** - instead of being given labelled
  examples, the agent explores and learns from the rewards its actions earn. An
  RL agent may contain a neural network (as in Deep RL), but its learning comes
  from reward, not from a fixed dataset.

## 5. Machine learning categories: supervised and unsupervised

Within ML, the two categories the syllabus names differ by whether the training
data carries labels.

| Aspect | Supervised learning | Unsupervised learning |
|---|---|---|
| Training data | **Labelled** - each example comes with the correct answer | **Unlabelled** - only the inputs, no answers |
| Goal | Learn a mapping from inputs to known outputs | Discover hidden structure or groupings in the data |
| What it produces | A classifier (categories) or a regression model (a number) | Clusters, groupings, or reduced-dimensionality data |
| Evaluation | Compare predictions against the known labels | Harder - no "right answer" to compare against |
| Example tasks | Spam vs not-spam, recognising digits, predicting house price | Customer segmentation, grouping similar news articles, anomaly detection |

The rule of thumb: if you can say "the correct answer for this example is X",
it is supervised; if you only have the data and must ask "what groups together?",
it is unsupervised.

## 6. Back propagation of errors and regression

### Back propagation of errors

**Back propagation of errors** (often just "backprop") is the method by which a
neural network adjusts its weights during supervised training. It works
backwards from the output error.

High-level steps:

1. **Forward pass** - feed a training example through the network; record the
   output the network actually produced.
2. **Compute the error** - compare the actual output with the correct (target)
   output using an error function (e.g. the difference, or squared error).
3. **Propagate the error backwards** - move from the output layer back through
   the hidden layers, working out how much each weight contributed to the
   error.
4. **Adjust the weights** - change each weight by a small amount in the
   direction that reduces the error (controlled by a **learning rate**).
5. Repeat over many examples until the network's errors are small enough.

The intuition: backprop assigns **blame** for the output error to each weight,
then nudges the weights so that next time the same input produces an output
closer to the target. (No code is required by the syllabus - only this
understanding.)

### Regression methods

**Regression** in machine learning means **predicting a continuous value** - a
number on a scale - rather than a category. This contrasts with
**classification**, which predicts a discrete label.

The simplest form is **linear regression**: fit a straight line through the
data points so that the line best predicts the output value from the input.
Given a set of input-output pairs, the line

$$y = mx + c$$

is chosen to minimise the total error between each real point and the line
(often the sum of squared differences). Once learned, the line can predict y
for any new x - for example, predicting a house's price from its floor area.

More complex regression (polynomial, multi-variable) fits curves or surfaces,
but the idea is the same: learn a function from inputs to a continuous output
by minimising prediction error on the training data.

## Worked-Thinking Routine

1. For a graph-structure question, name the three parts (nodes, edges,
   weights), say what each represents in the specific problem, and give one
   example of an edge and its weight.
2. For a Dijkstra question, keep the frontier table tidy: tentative distances
   in the columns, finalised nodes marked, and always pick the smallest next.
3. For an A\* question, state the formula `f = g + h`, define each term, and
   stress that h must never overestimate the true remaining cost.
4. For a Dijkstra-vs-A\* comparison, build the table from the guarantee
   (shortest path in both, but A\* uses a heuristic to focus the search).
5. For an ANN question, draw input → hidden → output layers, label the weights,
   and say that weights are *learned*, not programmed.
6. For ML/DL/RL, place them in a nesting: DL ⊂ ML; RL is a separate reward-based
   signal.
7. For supervised vs unsupervised, decide first whether the data is labelled -
   that single fact determines the category.
8. For back propagation, walk forward (compute output), then backward
   (propagate error, adjust weights) - in that order.
9. For regression, state that the output is a continuous value, and give the
   straight-line intuition before any detail.

## Common Mistakes

- Describing a graph without naming weights, or forgetting that weights
  represent cost.
- Thinking Dijkstra needs a goal - it finds shortest paths to *all* nodes; the
  goal is just where you stop.
- Saying A\* does not find the optimal path. It does, provided the heuristic is
  admissible.
- Using an inadmissible heuristic (one that overestimates) and still claiming
  optimality.
- Confusing the activation function with the weights. Weights scale inputs; the
  activation function decides the neuron's output.
- Treating Deep Learning as separate from Machine Learning. DL is a subset of
  ML.
- Confusing Reinforcement Learning with supervised learning: RL has no labelled
  examples, only a reward signal.
- Mixing up supervised and unsupervised by forgetting to check whether the data
  is labelled.
- Describing back propagation as adjusting weights to *increase* accuracy
  without mentioning it works *backwards from the error*.
- Calling regression "classification". Regression predicts a continuous value;
  classification predicts a category.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. Define a graph and name its three structural parts. Give an example of each
   in a routing problem.
2. Why is a graph a useful model for an AI search problem?
3. List the steps Dijkstra's algorithm performs, and state what it guarantees.
4. Trace Dijkstra by hand on a four-node weighted graph and state the order in
   which nodes are finalised.
5. State the A\* formula `f = g + h` and define g and h. What condition must h
   satisfy for A\* to remain optimal?
6. Give three differences between Dijkstra and A\*.
7. Draw the layers of an artificial neural network and explain what a weight
   does.
8. Why did neural networks help machine learning become practical on hard
   tasks?
9. Define Machine Learning, Deep Learning and Reinforcement Learning, and
   explain how they relate.
10. Give one reason to choose RL over supervised learning.
11. State the difference between supervised and unsupervised learning, with one
    example task each.
12. Describe the steps of back propagation of errors at a high level.
13. What does regression predict, and how does it differ from classification?
14. Give the equation of simple linear regression and say what is minimised to
    fit it.

## Connections

- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]]
  treats the **graph as an abstract data type** - the structure this topic
  searches is the same one you implement there.
- [[30 Computer Science/01 Topics/07 Ethics and Ownership/00 Overview|Ethics and Ownership]]
  is where the **impact and applications** of these AI methods are examined;
  this topic is the technical basis that underpins them.

## Study Sequence

1. Read section 1 and fix the three parts of a graph (nodes, edges, weights)
   with a routing example.
2. In section 2, learn Dijkstra's steps and the guarantee, then work the trace
   until the finalisation order is automatic.
3. Add A\* on top: same idea plus a heuristic, with the admissibility rule.
4. Memorise the Dijkstra-vs-A\* comparison table.
5. In section 3, draw an ANN and explain that weights are learned, not coded.
6. In section 4, place ML, DL and RL in a nesting and give one use for each.
7. In section 5, master the single test for supervised vs unsupervised: is the
   data labelled?
8. In section 6, walk back propagation forward then backward, and separate
   regression (continuous) from classification (discrete).
9. Self-check against the questions above before moving to worked examples.
