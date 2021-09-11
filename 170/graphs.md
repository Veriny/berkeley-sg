# Graphs

A graph is a pair of a set of vertices and set of edges. 

In a directed graph, order matters with respect to vertex-vertex pairs. In undirected graphs, order does not matter. If a vertex cannot have an edge to itself, the order does not matter.

Graphs can be **weighted**, meaning that edges have numbers associated with them. In a graph representing a road map, that number could be the number of miles to get from one vertex to another. 

## Computer Representations

We can represent vertices as a list of numbers.

There are two ways we can represent edges one is the **adjacency matrix,** where we have $$A_{ij} = 1 \implies (i,j) \in E$$and $$0$$otherwise. In a weighted graph, it would be $$W_{ij}$$instead of $$1$$, and $$\infty$$instead of $$0$$.

 

