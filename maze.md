# Maze Runner v.2


### Introduction
Welcome Adventurer! Your aim is to navigate a **2D array maze** and reach the finish point without touching any walls. Touching a wall will kill you instantly, and stepping outside the maze boundaries will also result in death.

### Task



The Maze array will look like
```c
maze = [[1, 1, 1, 1, 1, 1, 1]
        [1, 0, 0, 0, 0, 0, 0]
        [1, 0, 1, 0, 1, 0, 1]
        [1, 0, 0, 1, 1, 0, 1]
        [1, 0, 1, 0, 1, 3, 1]
        [1, 0, 1, 0, 1, 0, 1]
        [1, 2, 0, 0, 0, 0, 0]
        [1, 1, 1, 1, 1, 1, 1]]
```


You will be provided with:
1. A **2D array maze** where:
   - `0` = Safe place to walk
   - `1` = Wall (death)
   - `2` = Starting point
   - `3` = Finish point
2. A **string of directions** where:
   - `'N'` = Move North (up)
   - `'S'` = Move South (down)
   - `'E'` = Move East (right)
   - `'W'` = Move West (left)

Your task is to follow the directions in the order provided:
- If you reach the finish point (`3`) **before completing all moves**, return `"Finish"`.
- If you hit a wall (`1`) or go outside the maze boundary, return `"Dead"`.
- If you use all the moves and are still within the maze but not on the finish point, return `"Lost"`.



### Rules
1. The maximum size of the array is 64x64.
2. The maze will always be a **square 2D array** (`n x n`), but its size and content will vary.
3. Both the start and finish positions may change for each test.
4. The `directions` string will always be in uppercase (`'N'`, `'S'`, `'E'`, `'W'`).
5. Movement outside the maze boundaries will result in `"Dead"`.




### Sample Code
```c
#include <your_header>

char *solve_maze(const int maze[64][64], size_t n, const char *directions)
{
   // Your code here...
}

int main()
{
   const int maze1[64][64] = {
      {1, 1, 1, 1, 1, 1, 1},
      {1, 0, 0, 0, 0, 0, 0},
      {1, 0, 1, 0, 1, 0, 1},
      {1, 0, 0, 1, 1, 0, 1},
      {1, 0, 1, 0, 1, 3, 1},
      {1, 0, 1, 0, 1, 0, 1},
      {1, 2, 0, 0, 0, 0, 0},
      {1, 1, 1, 1, 1, 1, 1},
   };

   const int maze2[64][64] = {
      {1, 1, 1, 1, 1, 1, 1},
      {1, 0, 0, 0, 0, 0, 0},
      {1, 0, 1, 0, 1, 0, 1},
      {1, 2, 0, 1, 1, 0, 1},
      {1, 0, 1, 0, 1, 3, 1},
      {1, 0, 1, 0, 1, 0, 1},
      {1, 0, 0, 0, 0, 0, 0},
      {1, 1, 1, 1, 1, 1, 1},
   };

   // Test Case 1: Reach Finish successfully (output: Finish)
   const char *directions1a = "EEEENN";
   const char *directions1b = "SSSEEEENN";
   printf("Test 1A: %s\n", solve_maze(maze1, 8, directions1a));
   printf("Test 1B: %s\n", solve_maze(maze2, 8, directions1b));

   // Test Case 2: Hit a wall (output: Dead)
   const char *directions2a = "NNNNE";
   const char *directions2b = "SSSS";
   printf("Test 2A: %s\n", solve_maze(maze1, 8, directions2a)); 
   printf("Test 2B: %s\n", solve_maze(maze2, 8, directions2b)); 

   // Test Case 3: Run out of moves while still in the maze (output: Lost)
   const char *directions3a = "NNNNN";
   const char *directions3b = "SSSEENN";
   printf("Test 3A: %s\n", solve_maze(maze1, 8, directions3a)); 
   printf("Test 3B: %s\n", solve_maze(maze2, 8, directions3b)); 

   // Test Case 4:Out of bounds (output: Dead)
   const char *directions4a = "EEEEEEE";
   const char *directions4b = "NNEEEEEEE";
   printf("Test 4A: %s\n", solve_maze(maze1, 8, directions4b)); 
   printf("Test 4B: %s\n", solve_maze(maze2, 8, directions4b)); 

   return 0;
}

```
