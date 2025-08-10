# Question
Given an integer x, return true if x is a palindrome, and false otherwise.

##### Example:
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

# Optimal Solution

``` python
    def isPalindrome(self, x):
        temp=x
        if temp<0:
            return False
        rev=0
        x=abs(x)
        while(x>0):
            ldigit=x%10
            x=x//10
            rev=(rev*10)+ldigit
        if rev==temp:
            return True
        else:
            return False
        
```
### Time Complexity:O(logn)
### Space Complexity: O(1)
