# Question
Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.


##### Example:
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.


# Optimal


``` python
    def trap(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        n=len(height)
        leftmax=0
        rightmax=0
        index=0
        maxheight=height[0]
        total=0
        for i in range(n):
            if height[i]>maxheight:
                maxheight=height[i]
                index=i
        #left part
        for i in range(0,index):
            if leftmax>height[i]:
                total+=leftmax-height[i]
            else:
                leftmax=height[i]
        #right part
        for i in range(n-1,index,-1):
            if rightmax>height[i]:
                total+=rightmax-height[i]
            else:
                rightmax=height[i]
        return total
```
        

### Time Complexity:O(n)
### Space Complexity:O(1)
