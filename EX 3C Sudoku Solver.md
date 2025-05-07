# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1.Find the first empty cell in the Sudoku grid (usually represented by a 0).

2.Check if placing a number (1 to 9) in that cell is valid, based on Sudoku rules (row, column, and 3×3 box).

3.Try placing each number from 1 to 9 in the empty cell if it's valid.

4.Recursively repeat the process for the next empty cell (backtracking if no valid number fits).

5.If the grid is filled without conflict, the puzzle is solved; otherwise, backtrack to try other options.

## Program:
~~~
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: RAKSHITHA K
Register Number:  212223110039

board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    #####################  Add your code here #########################
    #Start here
    for i in range(0, 9):
        for j in range(0, 9):
            if board[i][j] == 0:
                for val in range(1, 10):
                    if isPossible(board, i, j, val):
                        board[i][j] = val
                        solve()
                        board[i][j] = 0
                return
    printBoard(board)
    #End here
solve()
~~~

## Output:
![image](https://github.com/user-attachments/assets/50cf83cb-e1aa-4429-b1db-18780f983dec)

## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
