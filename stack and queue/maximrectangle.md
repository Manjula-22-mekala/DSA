# Question

Given a rows x cols binary matrix filled with 0's and 1's, find the largest rectangle containing only 1's and return its area.


# Optimal Solution


``` python
    def maximalRectangle(self, matrix):
        """
        :type matrix: List[List[str]]
        :rtype: int
        """
        n=len(matrix)
        m=len(matrix[0])
        presum=[[0]*m for _ in range(n)]
        maxarea=0
        for j in range(m):
            sum=0
            for i in range(n):
                sum=sum+int(matrix[i][j])
                if int(matrix[i][j])==0:
                    sum=0
                presum[i][j]=sum
        for i in range(n):
            maxarea=max(maxarea,self.largestRectangleArea(presum[i]))
        return maxarea
                
    def largestRectangleArea(self, heights):
        """
        :type heights: List[int]
        :rtype: int
        """
        n=len(heights)
        st=[]
        maxarea=0
        for i in range(n):
            while(st and heights[st[-1]]>heights[i]):
                ele=st[-1]
                st.pop()
                nse=i
                pse=st[-1] if st else -1
                maxarea=max(maxarea,(nse-pse-1)*heights[ele])
            st.append(i)
        while(st):
            nse=n
            ele=st[-1]
            st.pop()
            pse=st[-1] if st else -1
            maxarea=max(maxarea,(nse-pse-1)*heights[ele])
        return maxarea
```

