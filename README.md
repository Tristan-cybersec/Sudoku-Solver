# Suduko-solver

Objective

The objective of this code is to solve a given Sudoku puzzle using a backtracking algorithm. Sudoku is a logic-based number placement puzzle where the player needs to fill a 9x9 grid so that each row, column, and 3x3 sub-grid contains all digits from 1 to 9 without repetition.

Skills Learned

- ' Backtracking Algorithm '- Understanding and implementing a recursive algorithm that tries - ----- possible solutions and backtracks if it encounters a dead end.
- ' Problem-Solving with Constraints '- How to ensure that certain constraints are met (like Sudoku - rules) while solving a problem.
- ' 2D List Manipulation '- Working with 2D lists (lists of lists) in Python to represent the Sudoku grid.
- ' Algorithm Optimization '- Learning to write efficient code that reduces unnecessary computations.

Tools Used


- ' Python Programming Language '- To implement the solution.
- ' IDE/Text Editor '- Any code editor like Visual Studio Code, PyCharm, or Jupyter Notebook can be used to write and run the Python code.
- ' Logical Reasoning '- To break down the problem and come up with a viable solution.


Step-by-Step


Ref 1 - Function



![function](https://github.com/user-attachments/assets/4a799f12-9fb4-436c-9424-cb67b55dd03e)

- ' board '- The 9x9 Sudoku grid, represented as a 2D list.
- ' row '- The row index of the cell where we're trying to place the number.
- ' col '- The column index of the cell where we're trying to place the number.
- ' num '- The number we want to place in the cell.


Ref 2 - Checking Row and Column



![Checking Row and Column](https://github.com/user-attachments/assets/7d8cf3a3-f25d-487e-81f7-4c37620a8e8b)


- The function first checks if the number ' num ' already exists in the same row ( ' row ' ) or the same column ( ' col ' ).
- If  ' num ' is found in either the row or the column, it returns ' False ', indicating that ' num ' cannot be placed in that cell.

Ref 3 - Checking the 3x3 Sub-grid



![Checking the 3x3 Sub-grid](https://github.com/user-attachments/assets/ff22fe96-beb1-4c53-afca-e6c1116d4de3)



- The Sudoku grid is divided into nine 3x3 sub-grids. This part of the function calculates the starting indices of the 3x3 sub-grid that contains the cell at ' board[row][col] '.
- It then checks if the number ' num ' is already present in that sub-grid.
- If ' num ' is found in the sub-grid, it returns ' False '.

Ref 4 - Returning True


![Returning True](https://github.com/user-attachments/assets/cb21632a-cdc5-41e0-bf93-abf151ff1674)

- If the number ' num ' is not found in the row, column, or 3x3 sub-grid, the function returns ' True ', indicating that it's valid to place ' num ' in the cell.


Ref 5 - Iterating Over the Board




![Iterating Over the Board](https://github.com/user-attachments/assets/90dd9230-18d9-41a4-aab8-02db4e1dba55)


- The function iterates through each cell of the board, checking for empty cells (' 0 ').
When it finds an empty cell at ' board[row][col] ', it proceeds to try placing numbers in that cell.



Ref 6 - Trying Numbers 1-9



![Trying Numbers 1-9](https://github.com/user-attachments/assets/a86e8456-95f2-40b3-a67b-3784d59f9c8a)


- For the empty cell found, the function tries placing numbers from 1 to 9.
- Before placing a number, it calls the ' is_valid ' function to check if the number can be placed there according to Sudoku rules.
- If ' is_valid ' returns ' True ', the number is temporarily placed in the cell ( ' board[row][col] = num ' ).




Ref 6 - Recursively Solving the Rest of the Board




![Recursively Solving the Rest of the Board](https://github.com/user-attachments/assets/d7d50f26-7eb3-4dd4-86ae-6e0535d5eec0)


- After placing a valid number in the cell, the function recursively calls itself ( ' solve_sudoku ' ) to attempt to solve the rest of the board.
- If the recursive call returns ' True ', the board is successfully solved, and the function returns ' True '.
- If placing a number in the current cell doesn't lead to a solution (returns ' False '), the function "backtracks" by resetting the cell to ' 0 '.
- The function then tries the next number from 1 to 9.
- If no valid number can be placed in the current cell, the function returns ' False ', indicating that the current configuration doesn't lead to a solution.
- If all cells are successfully filled with valid numbers, the function returns ' True ', indicating the Sudoku puzzle is solved.




Ref 7 - 



![Printing the Board](https://github.com/user-attachments/assets/0b95c65e-8882-4baa-be57-415b2f247675)



- ' board '- The 9x9 Sudoku grid, represented as a 2D list.
- The function iterates through each row of the board.
- It prints each row, replacing ' 0 ' with a dot (' . ') for readability.
- The numbers in each row are joined by spaces to form a visually appealing format.




Ref 8 - Input your Board



![input your board](https://github.com/user-attachments/assets/affa5024-a068-4afb-ba90-6d868b77b395)


- This section defines the Sudoku board as a 9x9 grid. Empty cells are represented by ' 0 '.



Ref 9 - Solving 





![Solving the Sudoku](https://github.com/user-attachments/assets/68919b7a-d143-4710-800a-eca446feae4b)



- The code calls the ' solve_sudoku ' function to attempt to solve the board.
- If the board is successfully solved, it prints "Sudoku solved successfully!" and then calls ' print_board ' to display the solved board.
- If no solution exists, it prints "No solution exists."













