# AI-Search-Algorithms

### - Breadth-First Search - BFS Algorithm (in Graph)
- Comlete: yes, always find the a solution
- Optimal: yes, always find the best solution
- Time Complexity: O(b^s), when: b - branching factor, s - tier of best the solution
- Space Complexity: O(b^s)
### Limited Depth-First Search - DFS-L Algorithm (in Tree)
- Comlete: no, solution might be deeper than *l*
- Optimal: no, optimal solution might be deeper than *l*
- Time Complexity: O(b^l), when: b - branching factor, l - depth limitation
- Space Complexity: O(b*l)
### - Depth-First Search - DFS Algorithm (in Tree)
- Comlete: no, can be stuck in a loop
- Optimal: no, can be stuck in a loop
- Time Complexity: O(b^m), when: b - branching factor, m - tier of first solution it sees ("leftmost") solution
- Space Complexity: O(b*m)
### - Iterative Deepening Depth-First Search - ID-DFS Algorithm (in Tree)
- Comlete: yes, always find the a solution 
- Optimal: yes, always find the best solution
- Time Complexity: O(b^s), when: b - branching factor, s - tier of best the solution
- Space Complexity: O(b*s)
### Weighted-A* Search - W-A* Algorithm (in Tree)
- Comlete: yes, always find the a solution
- Optimal: yes, always find the best solution
- Time Complexity: O(b^s), when: b - branching factor, s - tier of best the solution  
- Space Complexity: O(b*s)
### A*-epsilon Search - A*-Epsilon Algorithm (in Tree)
- Comlete: yes, always find the a solution
- Optimal: yes, always find the best solution
- Time Complexity: O(b^s), when: b - branching factor, s - tier of best the solution  
- Space Complexity: O(b*s)

#### We will use the above Algorithms to solve the following problem:

The Environment

![alt text](https://github.com/Almogbs/AI-Search-Algorithms/blob/main/env.png)

R, G, B, Y are locations on this map
The pipe symbol (|) represent walls
The colon symbol (:) represent open spaces

1.	The map is a 5x5 gridworld, leading to 25 locations.
2.	The alphabets R, G, B, Y are 4 locations.
3.	A passenger can be at any of the 4 locations.
4.	A passenger’s destination can be any of the left 3 locations.
5. The blue letter represents the current passenger pick-up location, and the purple letter is the current destination.
6.	The taxi can pass through **:** but not **|**
7.	The colon symbol **:** denotes a pass, which means, |B:a| if you’re at position **a** you can get to position **B** by going left.
8.	The pipe symbol **|** denotes a wall, which means, |Y|x: if you’re at position **x** you can’t get to position **Y** by going left.
9.	The environment rewards 20 points when a passenger is dropped to their destination.
10.	The environment penalizes -10 points if pickup operation is performed on a cell where there is no passenger.
11.	The environment penalizes -10 points if drop operation is performed if no passenger had boarded the taxi.
12.	The environment penalizes -1 for every other action.
13.	There are 500 states in this environment.

Each state answers these questions:
1.	Where is the taxi right now (one out of the 25 cells).
2.	Where is the passenger right now (one out of R,G,B,Y and the possibility of being inside the taxi).
3.	Where does the passenger want to go (one out of R,G,B,Y).

Initial conditions:
1.	At the start, the taxi will be at any of the 25 positions on the map.
2.	A passenger will be at any of R, G, B, Y locations.
3.	A destination will be at any of the R, G, B, Y locations.

Agent — Taxi

Our agent is a taxi, which can perform 6 actions:
0.	South
1.	North
2.  West
3.	East
4.	Pickup
5.	Dropoff

Expected behaviour

1.	The taxi must find the passenger traveling the shortest path.
2.	The taxi must pickup the passenger.
3.	The taxi must find the shortest path to the passenger’s destination.
4.	Drop the passenger at their destination traversing the shortest path
