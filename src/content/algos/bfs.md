---
title: 'BFS (Breadth-First Search)'
description: 'Graph'
pubDate: 'March 25 2024'
heroImage: ''
---

## Description
Simple algorithm for exploring a graph level by level. By starting from a given node (often called the 'start node'), it explores every nodes depth level by depth level.

## Brief History 
First description often attributed to Edsger Dijkstra, who described the algorithm as a method for finding the shortest path in a graph in his seminal paper "A Note on Two Problems in Connexion with Graphs" published in 1959.

## Properties 
- The algorithm is optimal if not weighted.
- The algorithm is complete (ensures that an optimal node is found if it exists).

## Complexity
| Case  | Space Complexity   | Time Complexity |
| :--- |:------|:-----|
| Worst Case  |  $\mathcal{O}(\|E\|+\|V\|) = \mathcal{O}(b^d)$       |  $\mathcal{O}(\|V\|) = \mathcal{O}(b^d)$ |

Where $E$ is the set of edges of the graph, $V$, its set of vertices, $b$, its branching factor and $d$ the distance (measured in number of edge traversals) from the start node. 

## Pseudocode
```
BFS(Graph G, Node root):
  Q = EmptyQueue()
  Q.enqueue(root)
  root.isExplored()
  WHILE (Q is not empty) :
    v = Q.dequeue()
    IF (v is goal) :
      return v
```