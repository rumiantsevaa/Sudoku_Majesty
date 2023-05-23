#include <iostream>
#include <vector>
using namespace std;

const int N = 9;

// printSudoku() : Function for displaying Sudoku on the screen.
void printSudoku(const vector<vector<int>>& sudoku) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            cout << sudoku[i][j] << " ";
        }
        cout << endl;
    }
}

// isSafe() : Function to check if a number can be placed in a certain Sudoku cell, according to the rules of the game.
bool isSafe(const vector<vector<int>>& sudoku, int row, int col, int num) {
    // Check if num does not occur in the same row and column.
    for (int i = 0; i < N; i++) {
        if (sudoku[row][i] == num || sudoku[i][col] == num) {
            return false;
        }
    }

    // Check if a num does not occur in the same small 3x3 square.
    int startRow = row - row % 3;
    int startCol = col - col % 3;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (sudoku[startRow + i][startCol + j] == num) {
                return false;
            }
        }
    }

    return true;
}

// solveSudoku() : Function for solving Sudoku by substitution method.
bool solveSudoku(vector<vector<int>>& sudoku) {
    int row, col;

    // Search for an empty cell (with value 0)
    bool isEmptyCell = false;
    for (row = 0; row < N; row++) {
        for (col = 0; col < N; col++) {
            if (sudoku[row][col] == 0) {
                isEmptyCell = true;
                break;
            }
        }
        if (isEmptyCell) {
            break;
        }
    }

    // If all cells are filled, then the sudoku is solved
    if (!isEmptyCell) {
        return true;
    }

    // Substitution of numbers from 1 to 9 in an empty cell
    for (int num = 1; num <= 9; num++) {
        if (isSafe(sudoku, row, col, num)) {
            sudoku[row][col] = num;

            // Recursive call to solve the rest of the Sudoku
            if (solveSudoku(sudoku)) {
                return true;
            }

            // If the current substitution does not lead to a solution, cancel it
            sudoku[row][col] = 0;
        }
    }

    return false;
}

int main() {
    vector<vector<int>> sudoku(N, vector<int>(N, 0));

    cout << "```````````````````````````````````````\n";
    cout << "WELCOME  TO  S U D O K U  M A J E S T Y\n";
    cout << "```````````````````````````````````````\n";
    cout << "3, 8, 9, 7, 0, 0, 2, 0, 0\n6, 7, 2, 0, 5, 0, 0, 1, 0\n0, 1, 4, 6, 0, 9, 0, 0, 3\n2, 3, 0, 5, 0, 0, 8, 7, 1\n8, 5, 0, 0, 3, 7, 0, 4, 9\n4, 9, 7, 8, 1, 0, 3, 0, 5\n0, 6, 5, 4, 8, 2, 1, 3, 0\n1, 0, 3, 0, 7, 0, 4, 6, 0\n7, 4, 0, 1, 0, 3, 5, 9, 0 ";
    cout << "\n___________________________________________________________________________\n";
    cout << "\nSelect a Sudoku array given below to solve (1) or enter Sudoku manually (2)\n";
    int choice;
    cin >> choice;

    switch (choice) {
    case 1:
        // Array 1
        sudoku = {
            {3, 8, 9, 7, 0, 0, 2, 0, 0},
            {6, 7, 2, 0, 5, 0, 0, 1, 0},
            {0, 1, 4, 6, 0, 9, 0, 0, 3},
            {2, 3, 0, 5, 0, 0, 8, 7, 1},
            {8, 5, 0, 0, 3, 7, 0, 4, 9},
            {4, 9, 7, 8, 1, 0, 3, 0, 5},
            {0, 6, 5, 4, 8, 2, 1, 3, 0},
            {1, 0, 3, 0, 7, 0, 4, 6, 0},
            {7, 4, 0, 1, 0, 3, 5, 9, 0}
        };
        break;

    case 2:
        // Array 2, Sudoku entered manually
        cout << "Enter a 9x9 Sudoku using numbers from 1 to 9 and zeros for gaps (each number must be divided with 'ENTER'):\n";

        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                cin >> sudoku[i][j];
            }
        }
        break;

    default:
        cout << "Incorrect choice.\n";
        return 0;
    }

    cout << "\nChosen Sudoku:\n";
    printSudoku(sudoku);

    if (solveSudoku(sudoku)) {
        cout << "\nSolution found:\n";
        printSudoku(sudoku);
    }
    else {
        cout << "\nSolution NOT found.\n";
    }

    return 0;
}
