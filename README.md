# CS50-AI-Problems

This repo contains problems from CS50 AI, for my own practice. I'll update the readme after each implementation and concepts. 
https://cs50.harvard.edu/ai/2020/

Implemented search using Depth First Search (Stack) and Breadth First Search (Queue).

maze.py is used to calculate the path from a starting to an end point, using DFS or BFS, reading from a file maze1.txt which has a starting point A and ending point B and paths blocked are represented by "#".

Usage : python maze.py maze1.txt

## Algorithm for BFS/DFS:
```
• Start with a frontier that contains the initial state.

• Start with an empty explored set.

• Repeat:
    • If the frontier is empty, then no solution.

    • Remove a node from the frontier.

    • If node contains goal state, return the solution.

    • Add the node to the explored set.

    • Expand node, add resulting nodes to the frontier if they aren't already in the frontier or the explored set.
```

## Degrees Search Problem

degrees/ folder has data from IMDB database and we have implemented BFS algorithm (QueueFrontier) to measure the shortest path between two actors or co-actors in movies. For example, if actors (a, b) are co-stars in a movie, and (b, c) and co-stars in another movie such that a and c have not worked together. Then we calculate the shortest degree of separation of actor a and c, which are related to b. Thus degree of freedom here is 2.

Usage: python degrees.py directory 

directory = "small" or "large"


## Tictactoe using Minimax

In a minimax problem:
```
• S0 : initial state
• PLAYER(s) : returns which player to move in state s
• ACTIONS(s) : returns legal moves in state s
• RESULT(s, a) : returns state after action a taken in state s
• TERMINAL(s) : checks if state s is a terminal state
• UTILITY(s) : final numerical value for terminal state s
```

The minimax algo and the funtion:

```
Minimax
• Given a state s:
• MAX picks action a in ACTIONS(s) that produces
highest value of MIN-VALUE(RESULT(s, a))
• MIN picks action a in ACTIONS(s) that produces
smallest value of MAX-VALUE(RESULT(s, a))

function MAX-VALUE(state):
 if TERMINAL(state):
 return UTILITY(state)
 v = -∞
 for action in ACTIONS(state):
 v = MAX(v, MIN-VALUE(RESULT(state, action)))
 return v

 function MIN-VALUE(state):
 if TERMINAL(state):
 return UTILITY(state)
 v = ∞
 for action in ACTIONS(state):
 v = MIN(v, MAX-VALUE(RESULT(state, action)))
 return v
```
#### Depth-Limited Minimax

Depth-limited Minimax considers only a pre-defined number of moves before it stops, without ever getting to a terminal state. However, this doesn’t allow for getting a precise value for each action, since the end of the hypothetical games has not been reached. To deal with this problem, Depth-limited Minimax relies on an evaluation function that estimates the expected utility of the game from a given state, or, in other words, assigns values to states. For example, in a chess game, a utility function would take as input a current configuration of the board, try to assess its expected utility (based on what pieces each player has and their locations on the board), and then return a positive or a negative value that represents how favorable the board is for one player versus the other. These values can be used to decide on the right action, and the better the evaluation function, the better the Minimax algorithm that relies on it.
