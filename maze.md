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

---

### Rules
1. The maze will always be a **square 2D array** (`n x n`), but its size and content will vary.
2. Both the start and finish positions may change for each test.
3. The `directions` string will always be in uppercase (`'N'`, `'S'`, `'E'`, `'W'`).
4. Movement outside the maze boundaries will result in `"Dead"`.


---

### Sample Code
```c
#include <your_header>

char *solve_maze(const int maze[10][10], size_t n, const char *directions)
{
   // Your code here...
}

int main()
{
    const int maze[10][10] = {
        {1, 1, 1, 1, 1, 1, 1},
        {1, 0, 0, 0, 0, 0, 0},
        {1, 0, 1, 0, 1, 0, 1},
        {1, 0, 0, 1, 1, 0, 1},
        {1, 0, 1, 0, 1, 3, 1},
        {1, 0, 1, 0, 1, 0, 1},
        {1, 2, 0, 0, 0, 0, 0},
        {1, 1, 1, 1, 1, 1, 1},
    };

    // Test Case 1: Reach Finish successfully (output: Finish)
    const char *directions1 = "EEEENN";
    printf("Test 1: %s\n", solve_maze(maze, 10, directions1));

    // Test Case 2: Hit a wall (output: Dead)
    const char *directions2 = "NNNNE";
    printf("Test 2: %s\n", solve_maze(maze, 10, directions2)); 

    // Test Case 3: Run out of moves while still in the maze (output: Lost)
    const char *directions3 = "NNNNN";
    printf("Test 3: %s\n", solve_maze(maze, 10, directions3)); 


    return 0;
}

```
