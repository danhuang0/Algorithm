# Graph

## Graph representations
### 1. Adjacency matrix
Adjacency matrix is a 2D array of size V * V where V is the number of vertices in a graph. 
* Undirected graph <br/>
In an unweighed graph, graph[i][j] = 1 indicates there is an edge between vertex i and vertex j. graph[i][j] = 0 indicates there is no edge between vertex i and vertex j. 

* Undirected weighted graph <br/>
In an undirected weighed graph, graph[i][j] = w indicates there is an edge between vertex i and vertex j with weight w. graph[i][j] = 0 indicates there is no edge between vertex i and vertex j.

* Directed graph <br/>
In a directed graph, graph[i][j] = 1 indicates there is an edge from vertex i to vertex j. graph[i][j] = 0 indicates there is no edge from vertex i to vertex j.

* Directed weighted graph <br/>
In a directed weighted graph, graph[i][j] = w indicates there is an edge from vertex i to vertex j with weight w. graph[i][j] = 0 indicates there is no edge from vertex i to vertex j.

### 2. Adjacency list

### 3. Adjacecy array

### 4. Edge list

### 5. Incidence matrix

## References
1. http://www.cs.cmu.edu/afs/cs/academic/class/15210-s12/www/lectures/lecture07.pdf
2. https://en.wikipedia.org/wiki/Graph_%28abstract_data_type%29#Representations
3. https://www.geeksforgeeks.org/graph-and-its-representations/
4. https://www.javatpoint.com/graph-theory-graph-representations#:~:text=In%20graph%20theory%2C%20a%20graph,to%20it%20by%20an%20edge).
5. https://en.wikipedia.org/wiki/Adjacency_list
