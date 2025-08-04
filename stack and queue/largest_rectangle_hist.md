# Question----solve cheyaliii

Given an array of integers heights representing the histogram's bar height where the width of each bar is 1, return the area of the largest rectangle in the histogram.
##### Example:
Input: heights = [2,1,5,6,2,3]
Output: 10

       
# Optimal
``` python
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
### Time Complexity:O(n)
### Space Complexity:O(n)
