# Question
Given an array of integers A and an integer B.

Find the total number of subarrays having bitwise XOR of all elements equals to B


##### Example:
Input:A = [4, 2, 2, 6, 4]
B = 6

output:4


# Optimal Solution

``` python
    def solve(self, A, B):
        mpp={}
        n=len(A)
        xor=0
        mpp[xor]=1
        cnt=0
        for i in range(n):
            xor=xor^A[i]
            x=xor^B
            if x in mpp:
                cnt=cnt+mpp.get(x)
            mpp[xor]=mpp.get(xor,0)+1
        return cnt
        #tc-o(n) and sc also
            
```
### Time Complexity:O(n)
### Space Complexity:O(n) 
