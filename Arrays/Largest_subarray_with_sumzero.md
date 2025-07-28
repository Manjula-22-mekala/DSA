# Question

Given an array arr[] containing both positive and negative integers, the task is to find the length of the longest subarray with a sum equals to 0.


##### Example:
Input: arr[] = [15, -2, 2, -8, 1, 7, 10, 23]

Output: 5

# Optimal Solution

``` python
    def maxLength(self, arr):
        # code here
        mpp={}
        sum=0
        maxlen=0
        for i in range(len(arr)):
            sum+=arr[i]
            if sum==0:
                maxlen=max(i+1,maxlen)
            elif sum in mpp:
                maxlen=max(maxlen,i-mpp[sum])
            else:
                mpp[sum]=i
        return maxlen
            
```
### Time Complexity:O(n)
### Space Complexity: O(n)-worstcase
