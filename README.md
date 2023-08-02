# Implementation-of-graph-in-python

In Python, you can implement a graph data structure using various approaches.
One common approach is to use dictionaries to represent the graph. There are two popular ways to represent a graph using dictionaries:

Adjacency List representation: Each vertex is associated with a list that contains its neighboring vertices.

Adjacency Matrix representation:
             It uses a 2D matrix to represent the connections between vertices.
             The matrix is typically implemented using a nested list or a 2D array.

Let's see how you can implement a graph using an adjacency list:

class Graph:
    def __init__(self):
        self.graph = {}

    def add_vertex(self, vertex):
        # Add a new vertex to the graph
        if vertex not in self.graph:
            self.graph[vertex] = []

    def add_edge(self, vertex1, vertex2):
        # Add an edge between vertex1 and vertex2 (assuming an undirected graph)
        self.add_vertex(vertex1)
        self.add_vertex(vertex2)
        self.graph[vertex1].append(vertex2)
        self.graph[vertex2].append(vertex1)

    def get_neighbors(self, vertex):
        # Get the neighbors of a vertex
        return self.graph.get(vertex, [])

    def __str__(self):
        # String representation of the graph
        return str(self.graph)


# Example usage:
if __name__ == "__main__":
    my_graph = Graph()
    my_graph.add_edge('A', 'B')
    my_graph.add_edge('A', 'C')
    my_graph.add_edge('B', 'C')
    my_graph.add_edge('B', 'D')

    print(my_graph)  # Output: {'A': ['B', 'C'], 'B': ['A', 'C', 'D'], 'C': ['A', 'B'], 'D': ['B']}
    print(my_graph.get_neighbors('B'))  # Output: ['A', 'C', 'D']
This implementation represents an undirected graph. 
If you want to implement a directed graph, you can modify the add_edge method to add an edge only from vertex1 to vertex2.

Remember that this is just one way to implement a graph in Python. Depending on the use case and specific requirements, you might choose a different representation or even use a graph library like NetworkX for more complex graph operations.
