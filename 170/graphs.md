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

**Alg 2:** Define a source as a vertex with no incoming edges and a sink as a vertex with no outgoing edges. Iteratively remove source vertices one at a time until we have a topological sort. This is a linear time algorithm, as each of the vertices gets to be a source once. Can be done in $$O(n + m)$$time.

**Alg 3: Using postorder numbers**: We claim that the vertex with the largest postorder number must be a source. $$Pf:$$if it's not a source, then there must be some vertex that is an in-vertex. If this was the case, there must be a back edge, but this is a DAG, and they don't have cycles, so that's impossible.

## Finding Strongly Connected Components

**Definitions:** $$(u,v)$$are strongly connected if $$u$$has a path to $$v$$and vice versa \(in a directed graph\). A strongly connected component is a maximal subset of strongly connected vertices. We can draw a graph on the strongly connected components, taking each subset as a graph.

**Algorithm 1:** Do $$n$$DFS, one from each vertex. 

**Algorithm 2:** Suppose we had a subroutine that allows us to peel off any sink inside of our SCC graph. Then, we could constantly peel the sinks off. Our runtime would be $$\sum_l C(n + m_l + o_l)$$where $$m_l$$are the number of edges within the component, and $$o_l$$are the number of edges leaving the component. The intuition is that, you keep a counter that keeps track of the name of the SCC that you are currently processing. Then, have an array that, for each vertex, it tells you the name of the SCC that the vertex is in. If you see an edge between the SCC and a vertex, you know that edge exists in the SCC graph. 

How to find a sink? Just find vertex in source SCC of the reversed original graph. Highest postorder number still works for this. 

## Minimum Spanning Tree

The spanning tree is a subgraph of G which contains all of the vertices in the graph and contains the minimum number of edges. The minimum spanning tree seeks to minimize the weights of the edges as well.

**Algorithm 1:** Use the cut strategy. When you partition a graph, the smallest edge in the partition is guaranteed to be in the MST.

**Algorithm 2:** Prim's Algorithm — initialize $$X$$as the empty set. Initialize $$S$$as $$\{s\}.$$Repeat the following $$n - 1$$times — supposing $$e$$is a min-weight edges crossing a subset of the graph $$S$$and $$V - S$$, if $$e = (a,b)$$then add $$a$$ to $$S$$and $$e$$ to $$X$$. Less formally, what we do is choose a vertex, then take the outgoing cheapest edge and add it to our tree. Then, we add the new vertex to our subset. Add the cheapest edge that goes out of the subset, and add the new vertex to the subset. Repeat until our subset contains all of the vertices in the graph.

**Algorithm 3:** Kruskal's Algorithm. First, sort $$E(G)$$in increasing order of weight. Create a UnionFind data structure. For increasing $$e$$, add $$e$$if $$Find(a) \neq Find(b)$$and then $$Union(a, b)$$. This prevents cycles. In layman's terms, add the smallest edge in the graph if it does not create a cycle, and do it over and over again until we have the MST.



