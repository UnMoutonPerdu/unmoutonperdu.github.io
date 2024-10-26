---
title: 'Algorithm - DFS (Depth-First Search)'
description: 'Algorithm - Graph traversal'
pubDate: 'March 28 2024'
heroImage: ''
---

## Description
DFS is another fundamental algorithm for graph traversal. Unlike the BFS, which doesn't explore nodes depth level by depth level, the DFS explores as deeply as possible, following certain edges before going back and exploring other areas.

## Properties 
- The algorithm is not optimal.
- The algorithm is not complete.
- The algorithm can loop indefinitely.

## Complexity
| Case  | Space Complexity   | Time Complexity |
| :--- |:------|:-----|
| Worst Case  |  $\mathcal{O}(\|V\|) = \mathcal{O}(bm)$       |  $\mathcal{O}(\|E\|+\|V\|) = \mathcal{O}(b^m)$ |

Where $E$ is the set of edges of the graph, $V$, its set of vertices, $b$, its branching factor and $m$ the depth of the deepest node. 

## Pseudocode - Recursive algorithm
```
DFS(Graph G, Node root):
  IF (root is goal):
    RETURN root
  root.isExplored()
  FOR EACH neighbor of v in G:
    IF neighbor has not been explored:
      DFS(G, neighbor)
```

## Pseudocode - Iterative algorithm
```
DFS(Graph G, Node root):
  S = EmptyStack()
  S.push(root)
  root.isExplored()
  WHILE (S is not empty):
    v = S.pop()
    IF (v is goal):
      RETURN v
    FOR EACH neighbor of v in G:
      IF neighbor has not been explored:
        neighbor.isExplored()
        S.push(neighbor)
```