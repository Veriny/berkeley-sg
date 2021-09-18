# Graphs

A graph is a pair of a set of vertices and set of edges. 

In a directed graph, order matters with respect to vertex-vertex pairs. In undirected graphs, order does not matter. If a vertex cannot have an edge to itself, the order does not matter.

Graphs can be **weighted**, meaning that edges have numbers associated with them. In a graph representing a road map, that number could be the number of miles to get from one vertex to another. 

## Computer Representations

We can represent vertices as a list of numbers.

There are two ways we can represent edges one is the **adjacency matrix,** where we have $$A_{ij} = 1 \implies (i,j) \in E$$and $$0$$otherwise. In a weighted graph, it would be $$W_{ij}$$instead of $$1$$, and $$\infty$$instead of $$0$$.

## Theorems

For $$u \neq v \in V$$, the $$[pre(x),post(x)]$$are either nested or disjoint.

Suppose $$(u, c) \in E$$. Then, $$post(u) < post(v) \iff (u, v) \text{ is a back edge}$$.

 $$\exists \text{back edge} \iff \exists \text{cycle in } G$$. 

## Topological Sort

The input is a "DAG", an directed graph with no cycles. Our goal is to output an ordering of the vertices such that if $$(u, v$$\) is an edge than $$u$$must come before $$v$$. This problem is unsolvable if there is a cycle in the graph. The topological sort does ot necessarily have to be unique.

In order to verify that a sort is topological, just check if the edge comes forward in the ordering. The maximium amount of topological sorts is $$n!$$, in the case of an unconnected graph.

### Possible topological sort algorithms

**The braindead brute force:** just try every possible permutation of the graph's nodes, check if they're topological.

**Alg 2:** Define a source as a vertex with no incoming edges and a sink as a vertex with no outgoing edges. Iteratively remove source vertices one at a time until we have a topological sort. This is a linear time algorithm, as each of the vertices gets to be a source once.

## Finding Strongly Connected Components

