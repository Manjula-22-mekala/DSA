# Question
You are given an undirected graph consisting of V vertices and E edges represented by a list edges[][], along with an integer m. Your task is to determine whether it is possible to color the graph using at most m different colors such that no two adjacent vertices share the same color. Return true if the graph can be colored with at most m colors, otherwise return false.

Note: The graph is indexed with 0-based indexing.
##### Example:
Input: V = 4, edges[][] = [[0, 1], [1, 3], [2, 3], [3, 0], [0, 2]], m = 3
Output: true
# Optimal Solution

``` python
     def graphColoring(self, v, edges, m):
        # Build adjacency list from the given edge list
        adj = [[] for _ in range(v)]
        for u, w in edges:
            adj[u].append(w)
            adj[w].append(u)

        # color array initialized with 0 (uncolored)
        color = [0] * v
        # Start solving from node 0
        if self.solve(0, adj, m, v, color):
            return True
        return False

    def solve(self, node, adj, m, n, color):
        if node == n:
            return True
        # Try all colors from 1 to m
        for c in range(1, m + 1):
            if self.is_safe(node, adj, color, c):
                color[node] = c
                if self.solve(node + 1, adj, m, n, color):
                    return True
                color[node] = 0  # backtrack
        return False

    def is_safe(self, node, adj, color, col):
        # Check all adjacent vertices
        for nei in adj[node]:
            if color[nei] == col:
                return False
        return True
```
### Time Complexity:O(n**m)
### Space Complexity: O(n)
