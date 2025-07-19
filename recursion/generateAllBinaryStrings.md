# Question

Given an integer N , Print all binary strings of size N which do not contain consecutive 1s.

A binary string is that string which contains only 0 and 1.


##### Example:
Input:N = 3

Output:000 , 001 , 010 , 100 , 101

# Optimal Solution


``` python
    def generateBinaryStrings(self, n):
        # Code here
        def gen(i,n,ans):
            if i >=len(n):
                ans.append("".join(n))
                return
            gen(i+1,n,ans)
            n[i]='1'
            gen(i+2,n,ans)
            n[i]='0'
        n=['0']*n
        ans=[]
        gen(0,n,ans)
        return ans
            
```
### Time Complexity:O(n.2^n)
### Space Complexity:O(n.2^n)
