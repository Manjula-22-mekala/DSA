# DFS

``` python 
    
    def findCircleNum(self, isConnected):

        n=len(isConnected)
        adj=[[] for _ in range(n)]
        for i in range(n):
            for j in range(n):
                if i!=j and isConnected[i][j]==1:
                    adj[i].append(j)
        visited=[0]*n

        def dfs(node):
            visited[node]=1
            for nei in adj[node]:
                if visited[nei]==0:
                    dfs(nei)

        provinces=0
        for i in range(n):
            if visited[i]==0:
                provinces+=1
                dfs(i)

        return provinces

            
```