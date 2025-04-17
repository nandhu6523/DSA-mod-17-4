# Data-Structures-using-Python-mod-17-4

## AIM :

To demonstrate the adjacency list representation of an undirected graph using linked lists in Python.

## ALGORITHM :

Step 1 : Define AdjNode class to create nodes representing vertices connected to a vertex.

Step 2 : Define Graph class to initialize a graph with V vertices and an adjacency list for each.

Step 3 : Use add_edge() to add edges:

a) Insert destination node at the beginning of source’s list.

b) Insert source node in destination’s list (because it’s undirected).

Step 4 : In print_graph(), for each vertex:

a) Print its index followed by all connected vertices using a while loop.

Step 5 : Traverse each adjacency list using temp = self.graph[i] and follow .next links.

Step 6 : Format the output to match the required display format.

Step 7 : Call print_graph() from the main driver code to show the full graph structure.

## PROGRAM :
```

class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print("Adjacency list of vertex {}\n head".format(i),end="")
	        temp=self.graph[i]
	        while temp:
	            print(" -> {}".format(temp.vertex),end="")
	            temp=temp.next
	        print(" \n")
# Driver program to the above graph class
if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()
```


## OUTPUT :

![image](https://github.com/user-attachments/assets/15e35e84-b75a-4bda-8ab9-e30a1c35ff40)

## RESULT :

Thus demonstration of the adjacency list representation of an undirected graph using linked lists in Python is successfully verified
