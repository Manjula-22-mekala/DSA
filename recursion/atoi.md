# Question


Whitespace: Ignore any leading whitespace (" ").


Signedness: Determine the sign by checking if the next character is '-' or '+', assuming positivity if neither present.


Conversion: Read the integer by skipping leading zeros until a non-digit character is encountered or the end of the string is reached. If no digits were read, then the result is 0.


Rounding: If the integer is out of the 32-bit signed integer range [-231, 231 - 1], then round the integer to remain in the range. Specifically, integers less than -231 should be rounded to -231, and integers greater than 231 - 1 should be rounded to 231 - 1.

 

##### Example:

Input: s = " -042"

Output: -42

Input: s = "words and 987"

Output: 0

Input: s = " -+87"

Output: 0

***

# Optimal Solution


``` python
    # iterative approach
    mini=-2**31
        maxi=2**31-1
        i=0
        n=len(s)
        while i<n and s[i]==' ':
            i=i+1
        sign=1
        if i < n and (s[i]=='+' or s[i]=='-'):
            if s[i]=='-':
                sign=-1
            i=i+1
        num=0
        while i<n and s[i].isdigit():
            digit=int(s[i])
            num=num*10+digit
            i=i+1
        num=num*sign
        if num<mini:
            return mini
        elif num>maxi:
            return maxi
        return num
    

        #using recursion
        mini=-2**31
        maxi=2**31-1
        s=s.lstrip()
        if not s:
            return 0
        sign=1
        if s[0]=='-':
            sign=-1
            s=s[1:]
        elif s[0]=='+':
            s=s[1:]
        def parse(i,num):
            if i>=len(s) or not s[i].isdigit():
                return num
            digit=int(s[i])
            num=num*10+digit
            return parse(i+1,num)
        num=parse(0,0)
        num=num*sign
        if num<mini:
            return mini
        elif num>maxi:
            return maxi
        return num
```
# for iterative approach
### Time Complexity: O(n)
### Space Complexity: O(1)

# for recursive approach
### Time Complexity: O(n)
### Space Complexity: O(n)