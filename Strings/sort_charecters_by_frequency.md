# Question

Given a string s, sort it in decreasing order based on the frequency of the characters. The frequency of a character is the number of times it appears in the string.


##### Example:
Input: s = "tree"

Output: "eert"

Explanation: 'e' appears twice while 'r' and 't' both appear once.
So 'e' must appear before both 'r' and 't'. Therefore "eetr" is also a valid answer.


# Optimal Solution


``` python
    def frequencySort(self, s):
        d={}
        for i in s:
            d[i]=d.get(i,0)+1
        sorted_dict=sorted(d.items(),key=lambda x:x[1],reverse=True)
        s=''
        for char,i in sorted_dict:
            s=s+(char*i)
        return s
            
```
### Time Complexity:O(n)
### Space Complexity: O(1) 
