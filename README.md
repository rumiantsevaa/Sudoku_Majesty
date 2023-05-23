# Sudoku_Majesty 
Main impovements compared to https://github.com/Balman123/Sudoku/blob/main/main_logic.cpp  
vector - used instead of array to fix too many initializer values error that occurs while trying to add mulptiple choices of array in Visual Studio. 
switch – used to provide a choice for the user whether to type manually or choose prepared Sudoku. 


(!) Main functions 
printSudoku() : Function for displaying Sudoku on the screen.
isSafe() : Function to check if a number can be placed in a certain Sudoku cell, according to the rules of the game.
solveSudoku() : Function for solving Sudoku by substitution method.

(!) Logic of program 
1.	Displaying Sudoku on the screen.
2.	Check if a number can be placed in a certain Sudoku cell, according to the rules of the game.
3.	Check if a num does not occur in the same small 3x3 square.
4.	Solving Sudoku by substitution method.
5.	Search for an empty cell (with value 0)
6.	If all cells are filled, then the sudoku is solved
7.	Substitution of numbers from 1 to 9 in an empty cell
8.	Recursive call to solve the rest of the Sudoku
9.	If the current substitution does not lead to a solution, cancel it
10.	Provide choice to user with case switch. 
11.	Display solution or results.

