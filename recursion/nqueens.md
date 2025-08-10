# Question
The n-queens puzzle is the problem of placing n queens on an n x n chessboard such that no two queens attack each other.

Given an integer n, return all distinct solutions to the n-queens puzzle. You may return the answer in any order.


##### Example:
Input: n = 4
Output: [[".Q..","...Q","Q...","..Q."],["..Q.","Q...","...Q",".Q.."]]
Explanation: There exist two distinct solutions to the 4-queens puzzle as shown above
 
# Optimal
``` python
    def solveNQueens(self, n):
        ans=[]
        board = [['.' for _ in range(n)] for _ in range(n)]
        column = [0] * n
        self.find(0,n,ans,board,column)
        return ans
    def find(self,row,n,ans,board,column):
        if row==n:
            ans.append([''.join(r) for r in board])
            return 
        for col in range(n):
            if column[col]==0 and self.check(n,board,row,col):
                column[col]=1
                board[row][col]='Q'
                self.find(row + 1, n, ans, board, column)
                column[col]=0
                board[row][col]='.'
    def check(self,n,board,row,col):
        #left diagonal
        r=row
        c=col
        while r>=0 and c>=0:
            if board[r][c]=='Q':
                return False
            r-=1
            c-=1
        #right diagonal
        r=row
        c=col
        while r>=0 and c<n:
            if board[r][c]=='Q':
                return False
            r-=1
            c+=1
        return True
            
```
### Time Complexity:O(n⋅n!)
### Space Complexity:O(k⋅n2)
