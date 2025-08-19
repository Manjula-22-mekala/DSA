# Question
The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.


##### Example:
Input: nums1 = [4,1,2], nums2 = [1,3,4,2]
Output: [-1,3,-1]
Explanation: The next greater element for each value of nums1 is as follows:
- 4 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
- 1 is underlined in nums2 = [1,3,4,2]. The next greater element is 3.
- 2 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.


### optimal solution
```python
    def nextGreaterElement(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: List[int]
        """
        n=len(nums2)
        st=[]
        nge={}
        for i in range(n-1,-1,-1):
            while(st and st[-1]<=nums2[i]):
                st.pop()
            if not st:
                nge[nums2[i]]=-1
            else:
                nge[nums2[i]]=st[-1]
            st.append(nums2[i])
        return [nge[num]for num in nums1]

```

### Time Complexity:O(n)
### Space Complexity: O(n)
