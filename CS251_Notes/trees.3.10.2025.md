Tree is an acyclic connected graph
They can be defined recursively. Any independent node can be a tree (subtree)
Top node is the root, nodes above a node are parents, nodes below are children.
Bottom nodes are leaves - any node with no children
Height is the length of the longest path from root to a leaf.

Number of nodes in a balanced tree = $2^{n+1}$ where $n$ is the height of the tree
There will be $2^{n}$ leaves at level $n$
The height will be $log_{2}(n)$ where $n$ is the number of nodes.
