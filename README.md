# Sudoku-Solver-in-C-
Given a partially filled 9×9 2D array ‘grid[9][9]’, the goal is to assign digits (from 1 to 9) to the empty cells so that every row, column, and subgrid of size 3×3 contains exactly one instance of the digits from 1 to 9.

Using backtracking algorithm, we will try to solve Sudoku problem. When some cell is filled with a digit, it checks whether it is valid or not. When it is not valid, it checks for other numbers. If all numbers are checked from 1-9, and no valid digit found to place, it backtracks to previous option.


-To solve this, we will follow these steps −

    Define a method called isPresentInCol(), this will take call and num

    for each row r in the grid, do

        if grid[r, col] = num, then return true
   
        return false otherwise

    Define a method called isPresentInRow(), this will take row and num

    for each column c in the grid, do

       if grid[row, c] = num, then return true

    return false otherwise

    Define a method called isPresentInBox() this will take boxStartRow, boxStartCol, num

    for each row r in boxStartRow to next 3 rows, do

        for each col r in boxStartCol to next 3 columns, do

            if grid[r, c] = num, then return true

    return false otherwise

    Define a method called findEmptyPlace(), this will take row and col

    for each row r in the grid, do

        for each column c in the grid, do

            if grid[r, c] = 0, then return true

    return false

    Define a method called isValidPlace(), this will take row, col, num

    if isPresentInRow(row, num) and isPresentInCol(col, num) and isPresntInBox(row – row mod 3, col – col mod 3, num) all are false, then return true

    Define a method called solveSudoku(), this will take the grid

    if no place in the grid is empty, then return true

    for number 1 to 9, do

        if isValidPlace(row, col, number), then

            grid[row, col] := number

            if solveSudoku = true, then return true

            grid[row, col] := 0

    return false
