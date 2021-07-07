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