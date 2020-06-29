# Depth First Search
Depth First Search (DFS) is an algorithm used to traversing or searching tree or graph data structures. The algorithm starts at the root node (select arbitrary nodes as the root nodes in the case of graph) and explores as far as possible along each branch before backtracing.

## Applications of DFS
#### 1. Find minimum spanning tree and shortest paths
For a weighted graph, DFS traversal of the graph produces the minmum spanning tree and all pair shortest path tree.
#### 2. Detect cycle in a graph. 
A graph has a cycle if and only if there is a back edge during DFS.
#### 3. Find paths between two given tertices u and v. 
(1) Call DFS(graph, u) (2) Use stack to track path between start node and current node (3) When destination node v is encountered, build the path as the content of the stack.
#### 4. Topological sorting.
#### 5. Test if a graph is bipartite
#### 6. Find strongly connected component
#### 7. Solve puzzles with only one solution


## References
1. https://en.wikipedia.org/wiki/Depth-first_search
2. https://www.geeksforgeeks.org/applications-of-depth-first-search/
