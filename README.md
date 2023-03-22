# Rate Maze Java
Problem Statement: A maze is provided in the form R * C matrix, where R is the total number of rows, and C is the total number of columns present in the matrix (R may or may not become equal to C). The cell m[0][0] is the source . From the source, the rat starts its journey. The rat has to reach cell m[R - 1][C - 1], the destination cell. The rat can move in upward (↑), downward (↓), rightward (→) leftward (←) directions from the cell where it is currently present. Also, note that the rat can only move to its adjacent cell.

This can be solved using Backtracking, Backtracking is an algorithmic-technique for solving problems recursively by trying to build a solution incrementally. Solving one piece at a time, and removing those solutions that fail to satisfy the constraints of the problem at any point of time (by time, here, is referred to the time elapsed till reaching any level of the search tree) is the process of backtracking.

Approach: The approach is to create a recursive method. The recursive method will follow a path starting from the source cell and will check whether the path reaches the destination cell or not. If the path is not successful in reaching the destination cell, then backtrack and try out the other paths.

Pseudocode for rat in maze problem: Begin

 1. If rat reaches the destination print the solution matrix. Else mark the current cell in solution matrix as 1. If previous step is not in vertical direction (upwards) then move forward in the vertical direction (downwards) and recursively check if this movement leads to solution. If movement in above step doesn’t lead to the solution and if previous step is not in horizontal direction (towards left) then move forward in the horizontal direction (towards right) and recursively check if this movement leads to solution.
 2. If movement in above step doesn’t lead to the solution and if previous step is not in vertical direction (downwards) then move forward in the horizontal direction(upwards) and recursively check if this movement leads to solution.
 3. If movement in above step doesn’t lead to the solution and if previous step is not in horizontal direction (towards right) then move forward in the horizontal direction (towards left) and recursively check if this movement leads to solution.
 4. If none of the above solution works then **BACKTRACK** and mark the current cell as 0.

**Input**: It will be in the form of nn or RC matrix. <br>
For example: <br>
{1, 0, 1, 1, 1} <br>
{1, 1, 1, 0, 1} <br>
{1, 0, 0, 1, 1} <br>
{1, 1, 0, 1, 0} <br>
{1, 0, 1, 1, 1}<br>

**Output**: <br>
{1, 0, 1, 1, 1} <br>
{1, 1, 1, 0, 1} <br>
{0, 0, 0, 1, 1} <br>
{0, 0, 0, 1, 0} <br>
{0, 0, 0, 1, 1}<br>
