# DFS

``` python 
    
    def floodFill(self, image, sr, sc, color):
        rows=len(image)
        cols=len(image[0])
        start_color=image[sr][sc]

        if start_color==color:
            return image
        
        def dfs(r,c):
            image[r][c]=color

            directions=[(-1,0), (0,1), (1,0), (0,-1)]
            for dr,dc in directions:
                nr,nc=r+dr,c+dc
                if (0<=nr<rows and 0<=nc<cols and image[nr][nc]==start_color):
                    dfs(nr,nc)
        dfs(sr,sc)
        return image

            
```