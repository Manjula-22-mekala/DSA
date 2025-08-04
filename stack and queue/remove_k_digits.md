# Question
Given string num representing a non-negative integer num, and an integer k, return the smallest possible integer after removing k digits from num.


##### Example:
Input: num = "1432219", k = 3
Output: "1219"
Explanation: Remove the three digits 4, 3, and 2 to form the new number 1219 which is the smallest.

# Optimal-sol without using set


``` python
    def removeKdigits(self, num, k):
        """
        :type num: str
        :type k: int
        :rtype: str
        """
        n=len(num)
        st=[]
        for i in num:
            while(st and k>0 and st[-1]>i):
                st.pop()
                k-=1
            st.append(i)
        while k>0:
            st.pop()
            k-=1
        result = ''.join(st).lstrip('0')
        return result if result else '0'
```
        


### Time Complexity:O(n)+o(k)
### Space Complexity:O(n)
