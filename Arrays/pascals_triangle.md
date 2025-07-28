# Question

Given an integer numRows, return the first numRows of Pascal's triangle.


##### Example:

Input: numRows = 5

Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]


# Optimal Solution

``` python
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        result=[]
        for i in range(1,numRows+1):
            result.append(self.generaterow(i))
        return result

    def generaterow(self,n):
        ans = 1
        res=[1] # printing 1st element

        #Printing the rest of the part:
        for i in range(1, n):
            ans = ans * (n - i)
            ans = ans // i
            res.append(ans)
        return res
            
```
### Time Complexity:O(n²)
### Space Complexity: O(n²)
