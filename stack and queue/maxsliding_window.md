# Question
You are given an array of integers nums, there is a sliding window of size k which is moving from the very left of the array to the very right. You can only see the k numbers in the window. Each time the sliding window moves right by one position.

Return the max sliding window.


##### Example:
Input: nums = [1,3,-1,-3,5,3,6,7], k = 3
Output: [3,3,5,5,6,7]
Explanation: 
Window position                Max
---------------               -----
[1  3  -1] -3  5  3  6  7       3
 1 [3  -1  -3] 5  3  6  7       3
 1  3 [-1  -3  5] 3  6  7       5
 1  3  -1 [-3  5  3] 6  7       5
 1  3  -1  -3 [5  3  6] 7       6
 1  3  -1  -3  5 [3  6  7]      7


### optimal solution
```python
    class Solution(object):
    def maxSlidingWindow(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: List[int]
        """
        st=deque()
        lit=[]
        for i in range(len(nums)):
            if st and st[0]<=i-k:
                st.popleft()
            while (st and nums[st[-1]]<=nums[i]):
                st.pop()
            st.append(i)
            if i>=k-1:
                lit.append(nums[st[0]])
        return lit
                

```



### Time Complexity:O(n-k)*k
### Space Complexity: O(n-k)
