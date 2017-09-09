## Chapter 4 - Trees and Graphs

### Trees

#### Binary Trees
Binary trees are a subset of tree where each parent node has a maximum of 2 child nodes. 

#### Binary Search Trees
Binary search tree is again a subset of a binary tree with the additional restriction that the value of left child nodes must be less than right nodes.

#### Complete Binary Trees
Complete binary trees are trees which are completely filled at all levels, with the possible exception of the last right-most node.

#### Full Binary Trees
A full binary tree is a tree where each node has either zero or two child nodes. Nodes can not have a single node.

#### Perfect Binary Tree
Meets the criteria of both full and complete binary trees. It is full at each level, and each node has the maximum number of child nodes (except at the last level). Perfect Binary Trees always have  2**k - 1 number of nodes, where k is the number of levels. 

#### Tries (Prefix Trees)
Tries are type of n-ary tree with characters stored in each node and each path from the root node represents a word. Tries allow word lookup in constant time O(n) where n is the length of the word. Useful for validating words against a preset list.

### Graphs
Graphs are a superset of trees (all trees are graphs but not all graphs are trees). Graphs have nodes connected by edges but there is no restriction on the number of connections per node.

#### Directed vs Undirected Graphs
The difference between directed and undirected graphs lies in the nature of the edges. In directed graphs, edges are unidirectional but in an undirected graph, they are bidirectional.

#### Connections
A graph need not have connections between every node. A graph can have isolated sub-graphs without connections between. If all nodes in the graph are connected, the graph is referred to as a 'connected graph'.



#### Graph Search

Depth-first Search
------------------
A depth-first search starts at a single node, then travels down a single branch at each subsequent node until it hits either a node it has already visited, or a dead end. This has the tendency to proceed 'far away' from the start node.

Example:
```
  def search(node)
    node.visit
    node.visited = true
    node.connections.each do |connection|
      search(connection) if connection.visited == false
    end
  end
```
Breadth-first Search
--------------------
A breadth-first starts at a given node, visits each connected node, then unvisited, connected nodes of each.

```
  def search(node)
    queue = []
    node.visited = true
    queue.push(node)

    while queue.any?
      n = queue.shift
      n.visit = true

      n.connections.each do |connection|
        if connection.visit == false
          connection.visit = true
          queue.push(connection)
        end
      end
    end
  end
```

Bi-directional Search
--------------------
A bidirectional search is used to find a path between 2 starting nodes by running two simultaneous breadth-first searches, until the two searches "meet" by visiting the same node.

