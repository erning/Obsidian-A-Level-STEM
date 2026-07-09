---
title: Artificial Intelligence Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[Artificial Intelligence](00%20Overview.md)"
status: active
tags:
  - computerscience/advanced
  - review-checklist
---

# Artificial Intelligence Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep the solutions out of sight until you can recall, trace, explain, and choose methods without prompting.

## Ideas to Recall

- [ ] Define a graph using nodes or vertices, edges or links, and weights.
- [ ] Explain how graphs model map-routing and state-space search problems.
- [ ] Distinguish directed and undirected graphs, and explain what an edge weight represents.
- [ ] Recall the Dijkstra terms frontier, tentative distance, finalised node, relaxation, and back-pointer.
- [ ] State what Dijkstra's algorithm guarantees when edge weights are non-negative.
- [ ] Recall the A\* formula `f = g + h`, where g is the exact cost so far and h is the heuristic estimate to the goal.
- [ ] State the admissibility condition for an A\* heuristic and why it matters.
- [ ] Describe an ANN using input, hidden, and output layers, with neurons connected by weights.
- [ ] Distinguish weights, bias, and activation functions in a neuron.
- [ ] Explain why learned weights made machine learning practical for tasks that are hard to hand-code.
- [ ] Define Machine Learning, Deep Learning, and Reinforcement Learning, including how DL relates to ML.
- [ ] Distinguish supervised and unsupervised learning by whether the training data is labelled.
- [ ] Recall the order of back propagation: forward pass, compute error, propagate error backwards, adjust weights.
- [ ] Define regression as predicting a continuous value, and recall the simple linear regression equation $y = mx + c$.

## Skills to Perform

- [ ] Model a named problem as a weighted graph by identifying the nodes, edges, weights, start node, and goal node.
- [ ] Draw or rewrite a small weighted graph from an edge list without losing any weights.
- [ ] Trace Dijkstra's algorithm using a tidy frontier table and finalise the smallest tentative distance each time.
- [ ] Recover the shortest path by following back-pointers from the goal to the start.
- [ ] Compare Dijkstra and A\* for a scenario and choose the better method from the goal and heuristic information.
- [ ] Identify whether a proposed A\* heuristic is likely to be admissible.
- [ ] Draw a simple ANN and label the input layer, hidden layer or layers, output layer, weights, and activation function.
- [ ] Choose between ML, DL, and RL for a scenario and justify the choice against the alternatives.
- [ ] Classify a dataset task as supervised or unsupervised and state what the system would produce.
- [ ] Describe back propagation in the correct order and state what the learning rate controls.
- [ ] Distinguish regression from classification and give a suitable task for each.
- [ ] Explain how a linear regression line is fitted by minimising prediction error.

## Things to Trace or Explain

- [ ] Trace how a real-world routing or game-state problem becomes nodes, edges, and weighted paths.
- [ ] Explain why Dijkstra never needs to revise a finalised node when weights are non-negative.
- [ ] Trace how a tentative distance is updated when a newly finalised node gives a cheaper route to a neighbour.
- [ ] Explain how A\* uses h to focus the search toward a single goal while still using exact cost g.
- [ ] Explain why A\* with `h = 0` behaves like Dijkstra's algorithm.
- [ ] Trace the data flow through an ANN from inputs to weighted sums, activation functions, and output.
- [ ] Explain why an ANN's learned weights are not the same thing as hand-written rules.
- [ ] Explain why RL uses rewards from an environment instead of labelled examples.
- [ ] Explain why unsupervised learning is harder to evaluate than supervised learning.
- [ ] Trace back propagation as a forward calculation followed by backwards error assignment and weight adjustment.
- [ ] Connect graph search to [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) and [Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md).
- [ ] Connect AI applications and limitations to [Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md).

## Common Errors to Avoid

- [ ] Describing a graph with nodes and edges but forgetting weights when the problem has costs.
- [ ] Treating Dijkstra as if it needs a heuristic or only works for one destination.
- [ ] Finalising a node before checking that it has the smallest tentative distance on the frontier.
- [ ] Losing the back-pointers, so the final distance is known but the path cannot be recovered.
- [ ] Claiming A\* is always optimal without saying that h must be admissible.
- [ ] Swapping g and h in `f = g + h`.
- [ ] Confusing an ANN weight with an activation function.
- [ ] Treating Deep Learning as separate from Machine Learning instead of as a subset.
- [ ] Calling an RL problem supervised just because there is feedback; rewards are not labels.
- [ ] Deciding supervised or unsupervised from the task name instead of checking whether labels are present.
- [ ] Describing back propagation as just "improving accuracy" without explaining the output error and backwards adjustment.
- [ ] Calling regression classification, or forgetting that regression predicts a continuous value.

## Ready to Move On When

- [ ] I can define a graph and use it to model a routing or state-space search problem.
- [ ] I can trace Dijkstra's algorithm by hand and recover both the shortest distance and the path.
- [ ] I can explain when A\* is preferable to Dijkstra and what condition keeps its heuristic safe.
- [ ] I can draw an ANN and explain how weights, bias, and activation functions work together.
- [ ] I can explain why learning weights from data is useful when explicit rules are too hard to write.
- [ ] I can choose between ML, DL, and RL for a scenario and name the learning signal each uses.
- [ ] I can decide whether a learning task is supervised or unsupervised from the presence or absence of labels.
- [ ] I can describe back propagation in order and explain the role of the learning rate.
- [ ] I can distinguish regression from classification and use $y = mx + c$ as the simple linear regression model.
- [ ] I can connect graph search in this topic to [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) and graph ADTs in [Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md).
- [ ] I can see how training data and model outputs connect to [Data Representation](../13%20Data%20Representation/00%20Overview.md).
- [ ] I can explain why AI's technical methods also need the impact and responsibility ideas in [Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md).
