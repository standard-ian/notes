#### Formal Definition:
A graph is an ordered triple (N, A ,g)
N = nonempty set of nodes (verticies V)
A = set of args (edged E)
g = function associating with each arc $a$ and unordered pair $x-y$ of nodes called the endpoints of an arc
![[Pasted image 20250303104036.png]]
#### Directed Graphs:
A directed graph is an ordered triple same as above, but a direction is associated with each arc. The inverse direction is NOT implied. 

#### Terminology:
Adjacent if nodes are endpoints of the same arc. 
Loop is an arch with endpoints n-n
Parallel Arcs two arcs with the same endpoint
Simply Graph is one with no loops or parallel arcs
Isolated node is adjacent to no other node.
Degree of a node is how many arcs end at that node. For a loop, count twice

In a directed graph:
	In Degree of vertex $V$ ($deg(v)$) is the number of edges with $v$ as their terminal vertex.
	Out Degree of vertex $V$ ($deg(v)$) is the number of edges with $v$ as their initial vertex.
	Loop contributes 1 to in and out degree of that node
	
Complete graph is one in which any two distinct nodes are adjacent. $K_{n}$ denotes the simple, complete graph with $n$ nodes. 

Subgraph of graph consists of a set of nodes and set of arcs that are exclusive subsets of the original node set and arc set, respectively, in which the endpoints of an arc must be the same nodes as in the original graph.

#### Other forms of Graphs
Labeled Graph - Nodes carry identifying information, like names of the cities on an airline route
Weighted Graph - Each arc has some numerical value or weight associated with it i.e. distance/routes.
Path from node to a node is a sequence of nodes. May contain the arcs, but has to contain the endpoints.
Reachable if a path exists from one node to another.
Length of a path is the number of arcs.
Connected if a path exists from any node to any other node
Cycle is a path from some node back to itself where no arc appears more than once in the path and the original node is the only one appearing more than once. 
A graph with no cycles is called acyclic

#### Greedy Strategy
Doing what looks best based on limited, immediate knowledge
When greedy strategy works, it leads to organization on a global level

#### Shortest Path Problem
Start with a simple weighted, connected graph where weights are positive. 
There exists a path between any two nodes x and y
Dijkstra's algorithm solves the shortest path problem for any 2 nodes.
Make a greedy choice at each vertex and evaluate the steps. 
Single source shortest path - find the shortest path from source vertex to all vertices. 
Works because an optimal path to destination node $v$ that passes through $x$ must also contain the optimal path to $x$
Feasible, Locally optimal, and Irrevocable, therefor greedy algorithm.
![[Pasted image 20250303115947.png]]

#### Euler Path and Hamiltonian Circuit Problems
###### Euler Paths
Seven bridges of Konigsberg - Find a walk through the city that would only cross each bridge only once. 
A Euler Path exists in a connected graph if and only if there are either no odd nodes or two odd nodes. 
For cases of no odd nodes, the path can being at any node and will end there. 
The theorem gives an algorithm to determine if an Euler path exists on an arbitrary connected graph. 
We make simplifying assumptions that the graph has no loops. 
