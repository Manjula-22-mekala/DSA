# Question
Given an array of integers arr, find the sum of min(b), where b ranges over every (contiguous) subarray of arr. Since the answer may be large, return the answer modulo 109 + 7.


##### Example:
Input: arr = [3,1,2,4]
Output: 17
Explanation: 
Subarrays are [3], [1], [2], [4], [3,1], [1,2], [2,4], [3,1,2], [1,2,4], [3,1,2,4]. 
Minimums are 3, 1, 2, 4, 1, 1, 2, 1, 1, 1.
Sum is 17.
       
# Optimal---incomplete 
``` python
    def sumSubarrayMins(self, arr):
        """
        :type arr: List[int]
        :rtype: int
        """
        mod=10**9 + 7
        nse_arr=self.nse(arr)
        psee_arr=self.psee(arr)
        n=len(arr)
        total=0
        for i in range(n):
            left=i-psee_arr[i]
            right=nse_arr[i]-i
            total+=(right*left*arr[i])%mod
        return total%mod
    def nse(self,arr):
        st=[]
        n=len(arr)
        nse_arr=[n]*n
        for i in range(n-1,-1,-1):
            while(st and arr[st[-1]]>=arr[i]):
                st.pop()
            if st:
                nse_arr[i]=st[-1]
            st.append(i)
        return nse_arr
    def psee(self,arr):
        st=[]
        n=len(arr)
        pse_arr=[-1]*n
        for i in range(n):
            while(st and arr[st[-1]]>arr[i]):
                st.pop()
            if st:
                pse_arr[i]=st[-1]
            st.append(i)
        return pse_arr
            
```
### Time Complexity:O(n)
### Space Complexity:O(1)
