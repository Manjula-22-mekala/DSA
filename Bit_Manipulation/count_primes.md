# Question
Given an integer n, return the number of prime numbers that are strictly less than n.


##### Example:
Input: n = 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.

# Optimal Solution


``` python
       def countPrimes(self, n):
        if n <= 2:
            return 0
        prime = [1] * n
        prime[0] = prime[1] = 0
        for i in range(2, int(n**0.5) + 1):
            if prime[i] == 1:
                for j in range(i * i, n, i):
                    prime[j] = 0

        return sum(prime)
```

