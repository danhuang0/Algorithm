# Depth First Search
Depth First Search (DFS) is an algorithm used to traversing or searching tree or graph. The algorithm starts at the root node of tree (or any arbitrary node of graph) and explores as far as possible before backtracing.

Particularly, the idea of DFS is to start from the root node of a tree or any arbitrary node of a graph, then mark the node and move the the next adjacent unmarked node. Repeat this loop until there is no unmarked adjacent nodes, then trackback and check for other unmarked nodes and traverse them.

## Pseudocode
- Recursive version:
```
procedure DFS(g, u) is
  mark u as visited
  foreach(adjacent node v of u in the graph)
    if(v is not visited)
      recursively call DFS(g, v)
```
- iterative version:
```
procedure DFS(g, u) is
  define a Stack 
  Stack.Push(u)
  while Stack is not empty
    curr = Stack.Pop();
    if curr is not marked as visited
      mark curr as visited
      foreach(adjacent node v of u in the graph)
        Stack.Push(v)
```

## DFS backtracing




  

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
3. http://www.cs.cmu.edu/afs/cs/academic/class/15210-s12/www/lectures/lecture09.pdf