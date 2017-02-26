# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: 

Constraint propagation is about assigning values, which satisfies or does not break some constraint. We can also think of this constraint as a condition or rule.

In Sudoku, the rule that a value must appear exactly once in each unit is a constraint that we can use to limit the possible positions of values, using the naked twins strategy.

The naked twins strategy detects pairs of boxes which contain only the same two elements, e.g. in the unit A1..A9, box A1 and box A6 could contain only the possible values 2 and 3. In this example, 2 and 3 must be in either A1 or A6, because these boxes have no other possible values, due to the constraint mentioned above. We can use this knowledge to remove these two values from the remaining boxes in the unit, so they no longer need to be considered for these other boxes.

This is what we are doing with the naked twins strategy: using a known constraint to assign new values to boxes other than the naked twins, that share possible values with the naked twins. In this case, the new values are the reduced set of possible values available for that particular box.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: 

Among the constraints for the Sudoku game is the set of units that we consider when solving the game puzzle.

With the diagonal Sudoku game, we are adding to these constraints by adding two new units, namely the diagonals of the game grid, i.e. A1, B2, C3 .. H8, I9 and A9, B8, C7 .. H2, I1. 

Note that nothing else changes about the game. We use the exact same strategies as before to solve the Sudoku puzzle, but we apply them to a new set of constraints, that contains the two new diagonal units, so every time we do for example a naked twins elimination, we do this on the diagonal units as well.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.