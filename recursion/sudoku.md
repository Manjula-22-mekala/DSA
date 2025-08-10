# Question

Write a program to solve a Sudoku puzzle by filling the empty cells.

A sudoku solution must satisfy all of the following rules:

Each of the digits 1-9 must occur exactly once in each row.
Each of the digits 1-9 must occur exactly once in each column.
Each of the digits 1-9 must occur exactly once in each of the 9 3x3 sub-boxes of the grid.
The '.' character indicates empty cells


##### Example:

### naive Solution--TLE


``` python
    class Solution(object):
        def solveSudoku(self, board):
            self.solve(board)
        def solve(self,board):
            for i in range(9):
                for j in range(9):
                    if board[i][j]=='.':
                        for c in map(str,range(1,10)):
                            if self.isValid(board, i, j, c):
                                board[i][j]=c
                                if self.solve(board):
                                    return True
                                else:
                                    board[i][j]='.'
                        return False
            return True
        def isValid(self, board, row, col, c):
            for i in range(9):
                if board[i][col] == c:
                    return False
                if board[row][i] == c:
                    return False
                # check 3x3 box
                if board[3*(row//3)+i//3][3 * (col // 3) + i % 3]==c:
                    return False
            return True

        
```
### Time Complexity:O(9**m) where m = number of empty cells
### Space Complexity: O(m) recursion depth

### optimal Solution--TLE


``` python
    def solveSudoku(self, board):
        rows = [set() for _ in range(9)]
        cols = [set() for _ in range(9)]
        boxes = [set() for _ in range(9)]

        # Fill initial state
        for r in range(9):
            for c in range(9):
                val = board[r][c]
                if val != '.':
                    rows[r].add(val)
                    cols[c].add(val)
                    boxes[(r // 3) * 3 + (c // 3)].add(val)

        def backtrack(r=0, c=0):
            if r == 9:
                return True
            if c == 9:
                return backtrack(r + 1, 0)
            if board[r][c] != '.':
                return backtrack(r, c + 1)

            box_index = (r // 3) * 3 + (c // 3)
            for digit in map(str, range(1, 10)):
                if digit not in rows[r] and digit not in cols[c] and digit not in boxes[box_index]:
                    board[r][c] = digit
                    rows[r].add(digit)
                    cols[c].add(digit)
                    boxes[box_index].add(digit)

                    if backtrack(r, c + 1):
                        return True

                    # Backtrack
                    board[r][c] = '.'
                    rows[r].remove(digit)
                    cols[c].remove(digit)
                    boxes[box_index].remove(digit)

            return False

        backtrack()

        
```
### Time Complexity:O(9**m) where m = number of empty cells
### Space Complexity: O(1) recursion depth
