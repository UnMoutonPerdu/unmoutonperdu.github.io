---
title: 'Algorithm - A*'
description: 'Algorithm - Graph traversal - Path Finding'
pubDate: 'April 2 2024'
heroImage: ''
---

## Description
A* algorithm is a popular and widely used pathfinding algorithm in computer science and artificial intelligence. It is an extension of the Dijkstra's algorithm with a heuristic function added to improve efficiency.

## Properties 
- On finite graphs A* is guaranteed to terminate and is complete only if there is no negative edge weight.
- On infinite graph with a finite branching factor and edges costs that are strictly positive, A* is guaranteed to terminate only if a solution exists.
- A* is optimal in tree search if the heuristic is admissible.
- A* is optimal in graph search if the heuristic is consistent.

## Complexity
| Case  | Space Complexity   | Time Complexity |
| :--- |:------|:-----|
| Worst Case  |  $\mathcal{O}(\|E\|log(\|V\|)) = \mathcal{O}(b^d)$       |  $\mathcal{O}(\|V\|) = \mathcal{O}(b^d)$ |

Where $E$ is the set of edges of the graph, $V$, its set of vertices, $b$, its branching factor and $d$ the depth of the solution. 

## Pseudocode 
```
A*(Graph G, Node start, Node goal, Heuristic h):
  openList = emptyPriorityQueue()
  closeList = emptyPriorityQueue()
  openList.enqueue(start)
  WHILE (openList is not empty) :
    v = openList.dequeue()
    IF (v is goal) :
      RETURN reconstructPathFrom(v)
      BREAK
    FOR EACH (neighbor of v) :
      newCost = h(neighbor)
      IF ((neighbor not in closeList) AND (neighbor not in openList with neighbor.cost < newCost)) :
        neighbor.parent = v
        neighbor.cost = newCost
        openList.enqueue(neighbor)
    closeList.enqueue(v)
```