# Question
Given a number n. Find its unique prime factors in increasing order.

##### Example:
Input: n = 100
Output: [2, 5]
Explanation: Unique prime factors of 100 are 2 and 5.

# Optimal Solution


``` python
        def primeFac(self, n):
        l=[]
        m=int(math.sqrt(n))
        for i in range(2,m+1):
            if n%i==0:
                l.append(i)
                while(n%i==0):
                    n=n//i
        if n!=1:
                l.append(n)
        return l
```

