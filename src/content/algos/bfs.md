---
title: 'BFS (Breadth-First Search)'
description: 'Graph traversal'
pubDate: 'March 25 2024'
heroImage: ''
---

## Description
BFS is a fundamental algorithm for exploring a graph depth level by depth level. It starts with a given node (often called the 'start node'), and it explores every nodes level by level until the 'goal node' is found.

## Brief History 
The first description is often attributed to Edsger Dijkstra, who described the algorithm as a method for finding the shortest path in a graph in his seminal paper "A Note on Two Problems in Connexion with Graphs" published in 1959.

## Properties 
- The algorithm is optimal if not weighted.
- The algorithm is complete (ensures that an optimal node is found if it exists).

## Complexity
| Case  | Space Complexity   | Time Complexity |
| :--- |:------|:-----|
| Worst Case  |  $\mathcal{O}(\|V\|) = \mathcal{O}(b^d)$       |  $\mathcal{O}(\|E\|+\|V\|) = \mathcal{O}(b^d)$ |

Where $E$ is the set of edges of the graph, $V$, its set of vertices, $b$, its branching factor and $d$ the distance (measured in number of edge traversals) from the start node to the nearest solution. 

## Pseudocode
```
BFS(Graph G, Node root):
  Q = EmptyQueue()
  Q.enqueue(root)
  root.isExplored()
  WHILE (Q is not empty):
    v = Q.dequeue()
    IF (v is goal):
      return v
    FOR each neighbor of v in G:
      IF neighbor has not been explored:
        neighbor.isExplored()
        Q.enqueue(neighbor)
```