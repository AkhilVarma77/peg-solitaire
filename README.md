**Python Peg Solitaire Solver**
This project provides a Python implementation of a solver for the classic game of Peg Solitaire. It uses a graphical user interface (GUI) built with tkinter to visualize the board and the solution process. The program finds a sequence of moves to reach the final state (a single peg remaining) using search algorithms.

**Features**
--> Graphical Interface (GUI): Displays the Peg Solitaire board, pegs, and empty slots in a simple window.

--> Automated Solving: Implements search algorithms to find a solution from the standard starting position.

--> Two Search Algorithms: Includes implementations for both a standard Depth-First Search (DFS) and a simple Goal-Based Agent.

--> Solution Visualization: Once a solution is found, the program animates each move on the GUI, allowing you to watch the puzzle being solved.

**How It Works**
The program operates by treating the puzzle as a state-space search problem. Each configuration of the board is a "state," and a valid move transitions the board from one state to another. The goal is to find a path from the initial state to a goal state.

**Board Representation**
The game board is represented by a 7x7 2D list (a list of lists). Each cell in the list has one of three integer values:

--> 1: Represents a space occupied by a peg.
--> 0: Represents an empty hole.
--> -1: Represents an invalid position (the corners of the square grid that are not part of the cross-shaped board).

**Search Algorithms**
The solver uses recursive, depth-first-style search to explore the game tree. To prevent infinite loops and redundant calculations, it keeps a set of visited_states.

**Depth-First Search (solve_with_dfs)**
This function implements a classic DFS algorithm. It explores as far as possible along each branch before backtracking. It works by:

--> Checking if the current board is the solved state (base case).
--> Returning if the current board state has already been visited.
--> Recursively calling itself for every possible valid move from the current state.
--> Passing the current path of moves down through the recursion, so when a solution is found, the entire path is immediately available.

**Goal-Based Agent (solve_with_goal_based_agent)**
This function demonstrates a simple goal-based agent. In Artificial Intelligence, a goal-based agent is one that has a specific goal it tries to achieve. In this case, the goal is to reach a board state with only one peg.

--> Implementation: The strategy used by this agent is a recursive search that is functionally equivalent to DFS. It explores possible moves until it finds a path to the goal. The main difference in the code is how the solution path is constructed. Instead of passing the path down, it's rebuilt backwards as the successful recursive calls return.


**Code Structure Overview**

--> initialize_gui(): Creates the main tkinter window and canvas.
--> draw_board(board): Renders the current state of the board on the canvas.
--> solve_with_dfs(board, path): The primary DFS solver function.
--> solve_with_goal_based_agent(board): The Goal-Based Agent solver function.
--> get_next_boards(board): A successor function that generates all possible board states reachable from the current state in one move.
--> is_valid_move(...): A helper function that checks if a specific jump is legal.
--> is_solved(board): The goal test function. It returns True if there is only one peg left on the board.
--> board_to_key(board): Converts the board (a list of lists) into a hashable tuple so it can be stored in the visited_states set.
--> visualize_solution(root): Iterates through the stored solution steps and calls draw_board to animate them.
--> main(): The main execution function that initializes the program, calls the solver, and starts the GUI loop.



<img width="527" height="573" alt="image" src="https://github.com/user-attachments/assets/8bb7f8e4-9a23-4dec-9f36-91608ac7270a" />
<img width="524" height="567" alt="image" src="https://github.com/user-attachments/assets/0b60f7ac-5c13-474c-911c-95b6dffd99b1" />
