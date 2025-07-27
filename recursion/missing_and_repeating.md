# Question

Given an unsorted array arr[] of size n, containing elements from the range 1 to n, it is known that one number in this range is missing, and another number occurs twice in the array, find both the duplicate number and the missing number.


##### Example:
Input: arr[] = [2, 2]

Output: [2, 1]

Explanation: Repeating number is 2 and the missing number is 1.


# Optimal Solution


``` python
    def findTwoElement(self, arr):
        # code here
        n=len(arr)
        s1=0
        s2=0
        x,y=0,0
        val1,val2=0,0
        s1n=(n*(n+1))//2
        s2n=(n*(n+1)*(2*n+1))//6
        for i in arr:
            s1=s1+i
            s2=s2+(i*i)
        val1=s1-s1n
        val2=s2-s2n
        val2=val2//val1
        x=(val1+val2)//2
        y=val2-x
        return [x,y]
        #tc-0(n),sc-o(1)
            
```
### Time Complexity:O(n)
### Space Complexity: O(1)--not using any Data structure---got rid off 
