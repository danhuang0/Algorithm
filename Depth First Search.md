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
  let S be a Stack 
  S.Push(u)
  while S is not empty
    v = Stack.Pop();
    if v is not marked as visited
      mark v as visited
      foreach(adjacent node w of v in the graph)
        Stack.Push(w)
```

## DFS backtracing
![image](https://github.com/idanhuang/DataStructure-and-Algorithm/blob/master/image/DFS_backtracing.png) <br/>
DFS will explore a path as far as possible. When there are no more vertex along the current path can be expored, DFS move backwards on the same path to find vertex to traverse. All the vertex on the current paths will be visited before the next path will be selected.

Example 1: In the left graph, DFS will start from vertex s, then vertices 1, 2 and 3 (suppose DFS choose 1 before 4). After visiting vertex 3, DFS hits a dead end and will back out to 2 then back to 1. Then DFS will select the next path to explore, DFS will visit vertices 4, 5 and 6 successively. When hitting vertex 6, DFS will back out to 5, 4 and s.

Example 2: In the right graph, DFS will start from vertex s, then vertices 1, 2, and 3 (suppose DFS choose 3 before 5 when at vertex 2). When hit a dead end at vertex 3, DFS back out to 2, then traverse vertex 5, then to 4. Then back out to 5 before travering vertex 6. Then DFS will back out to 5, then 2 then 1, then s.

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
4. https://www.hackerearth.com/practice/algorithms/graphs/depth-first-search/tutorial/
