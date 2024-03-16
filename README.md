# Knapsack

# Knapsack Algorithm

## Description
Dijkstra's Algorithm is an algorithm used to solve the single source shortest path problem, which uses greedy algorithms to gradually expand the set of known shortest paths until reaching the target node.

![Image Title](Dijkstra.png)

## Gold
Given a weighted directed graph and a source node to find the shortest path from the source node to all other nodes in the graph.

## Pseudocode

```

```
### Algorithmic principle
The Dijkstra algorithm uses a greedy algorithm to gradually expand the set of known shortest paths until reaching the target node. Specifically, the algorithm maintains a distance array that records the shortest distance from the starting node to each node, as well as a set that records the nodes that have determined the shortest path. At each step, the algorithm selects the node with the smallest distance in the distance array that is not in the set, adds it to the set, and updates the distance array to reflect the shortest path from the starting node to that node.
>


## Algorithm application
Dijkstra Algorithm is commonly used in search engines. Many websites use this algorithm to generate product links or push videos that users may be interested in. 
>
Another application of Dijkstra in daily life is reflected in logistics and transportation. Logistics companies typically use this algorithm to optimize routes, allocate goods, manage traffic flow, and other areas to improve efficiency and reduce costs.


## Algorithm implement
The Implementation of Algorithms in C++
```


```

## Time complexity
For a graph with V vertices and E edges, the time complexity of the Dijkstra algorithm is:
- Implement using adjacency matrix: O(V<sup>2</sup>).
- Implement priority queue using binary heap: O((V+E)logV) .
### Worse case
The worst-case time complexity is O((V<sup>2</sup> + E) log V). This is because even with heap optimization, each vertex may be inserted, deleted, and updated, with each of these operations having a time complexity of log V. If E approaches V<sup>2</sup>, then the overall complexity of heap operations may approach O(V<sup>2</sup> log V).

## Results
