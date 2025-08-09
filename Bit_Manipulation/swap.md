# Question
You are given two numbers a and b. Your task is to swap the given two numbers


##### Example:
Input: a = 13, b = 9
Output: 9 13
Explanation: After swapping it becomes 9 and 13.

# Optimal Solution

``` python
    def get(self, a: int, b: int) -> tuple[int, int]:
        # code here
        a=a^b
        b=a^b
        a=a^b
        return a,b         
```

