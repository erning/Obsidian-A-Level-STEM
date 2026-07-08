---
title: Artificial Intelligence Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/18 Artificial Intelligence/00 Overview|Artificial Intelligence]]"
status: active
tags:
  - computerscience/advanced
  - practice
---

# Artificial Intelligence Key Practice Problems

Work through these without looking at the solutions. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. For graph traces, keep a tidy frontier table and always finalise the smallest tentative distance. For learning methods, decide first whether the data is labelled, then whether the output is continuous or categorical. Candidates are not required to write graph algorithms.

## A. Graphs and search

1. Define a graph and name its three structural parts. For a map-routing problem, state what each part represents and give one example of each.

2. Explain why a graph is a useful model for an AI search problem, and give two distinct uses of graphs in AI other than map routing.

3. A graph is undirected with edge set A-B 10, A-C 4, B-C 5, B-D 6, C-D 2, D-E 7. Draw the graph (ASCII) and state what the weights represent.

4. Using the edge set in question 3, run Dijkstra's algorithm from A to E. Give the finalisation order of the nodes and the shortest distance from A to E.

5. Using the same edge set, state the shortest path from A to B and its distance, and explain how you read the path off the finalised table.

6. State what Dijkstra's algorithm guarantees, and explain why a finalised node never needs to be revised.

7. A\* uses the formula `f = g + h`. Define g, h, and f, and state the condition h must satisfy for A\* to remain optimal. Give one example of a suitable h for a road map.

8. A delivery app needs one route from a depot to a single customer on a city road map, and a reliable straight-line distance to the destination is available. Recommend either Dijkstra or A\* and justify your choice against the other.

## B. Neural networks

9. Draw the layers of an artificial neural network (ANN) and label the input layer, hidden layer(s), and output layer.

10. Explain what a weight does in an ANN, and distinguish the weight from the activation function.

11. Explain why the fact that weights are *learned* from data, rather than hand-programmed, made machine learning practical on tasks such as image recognition or speech.

## C. Learning methods

12. Define Machine Learning (ML), Deep Learning (DL), and Reinforcement Learning (RL), and explain how the three relate (including which is a subset of which).

13. For each task, choose ML, DL, or RL and justify it against the other two:
    - (a) Filtering spam from a large labelled archive of emails.
    - (b) Translating text between languages from large parallel corpora.
    - (c) Learning to play chess by playing many games and winning or losing.

14. Give one reason to choose Reinforcement Learning over supervised learning, and state what learning signal each uses.

15. For each scenario, state whether it is supervised or unsupervised learning, give one reason, and name what the system would produce:
    - (a) A dataset of houses, each with its known selling price, used to predict prices of new houses.
    - (b) A dataset of customer browsing logs with no labels, used to group similar customers together.

16. State the single fact that determines whether a learning task is supervised or unsupervised, and explain why evaluation is harder for unsupervised learning.

## D. Back propagation and regression

17. Describe the back propagation of errors process at a high level, in the correct order, and state what the learning rate controls.

18. Explain why back propagation is said to work *backwards from the error*, and state which step computes the comparison between actual and target output.

19. Explain what regression means in machine learning and how it differs from classification. Give one example task for each.

20. Give the equation of simple linear regression. State what is minimised to fit the line, and give one example of a value that could be predicted with it.
