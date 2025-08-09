# Question
Given a 32 bit unsigned integer num and an integer i. Perform following operations on the number - 

1. Get ith bit

2. Set ith bit

3. Clear ith bit

##### Example:
Input: 70 3
Output: 1 70 66
Explanation: Bit at the 3rd position from LSB is 1. (1 0 0 0 1 1 0) .The value of the given number after setting the 3rd bit is 70. The value of the given number after clearing 3rd bit is 66. (1 0 0 0 0 1 0)


# Optimal Solution

``` python
    def bitManipulation(self, num, i):
        # Code here
        i = i - 1 

        print((num >> i) & 1, num | (1 << i), num & ~(1 << i))
            
```

