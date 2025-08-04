# Question
 A celebrity is a person who is known to all but does not know anyone at a party. A party is being organized by some people. A square matrix mat[][] (n*n) is used to represent people at the party such that if an element of row i and column j is set to 1 it means ith person knows jth person. You need to return the index of the celebrity in the party, if the celebrity does not exist, return -1.

##### Example:
Input: mat[][] = [[1, 1, 0], [0, 1, 0], [0, 1, 1]]
Output: 1
Explanation: 0th and 2nd person both know 1st person. Therefore, 1 is the celebrity person. 


### optimal solution
```python
     def celebrity(self, mat):
        # code here
        top=0
        down=len(mat)-1
        while(top<down):
            if mat[top][down]==1:
                top=top+1
            elif mat[down][top]==1:
                down=down-1
            else:
                top=top+1
                down=down-1
        if top>down:
            return -1
        flag=False
        for i in range(len(mat)):
            if i==top:
                continue
            if mat[top][i]==0 and mat[i][top]==1:
                flag=True
            else:
                return -1
        return top

```



### Time Complexity:O(n)
### Space Complexity: O(1)
