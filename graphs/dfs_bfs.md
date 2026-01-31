# DFS

``` python 
    
    def dfsOfGraph(self, V, adj):
        visited=[False]*V
        result_dfs=[]
        def dfs(node):
            visited[node]=True
            result_dfs.append(node)
            for nei in adj[node]:
                if not visited[nei]:
                    dfs(nei)
        dfs(0)
        return result_dfs

            
```
# BFS
``` python
    from queue import Queue   
    def bfsOfGraph(self, V, adj):

        visited=[False]*V
        q=Queue()
        q.put(0)
        visited[0]=True
        bfs=[]
        while not q.empty():
            node=q.get()
            bfs.append(node)
            for nei in adj[node]:
                if not visited[nei]:
                    visited[nei]=True
                    q.put(nei)
        return bfs
        
        
            
```