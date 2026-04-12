# Number of Islands
# Use DFS to traverse the grid, and whenever a '1' is found, recursively mark all its connected land cells as '0' (sink the island) and increment the island count.

# Time Complexity: O(m × n) — each cell is visited once
# Space Complexity: O(m × n) (worst case recursion stack when grid is all land)

# CODE
class Solution {

    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0) return 0;
        
        int count = 0;
        int rows = grid.length;
        int cols = grid[0].length;

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                // If we find land, it's a new island
                if (grid[i][j] == '1') {
                    // Sink the island using DFS
                    dfs(grid, i, j);
                    count++;
                }
            }
        }
        return count;
    }

    private void dfs(char[][] grid, int r, int c) {
        int rows = grid.length;
        int cols = grid[0].length;

        if (r < 0 || c < 0 || r >= rows || c >= cols || grid[r][c] == '0') {
            return;
        }

        grid[r][c] = '0';

       dfs(grid, r + 1, c); // Down
        dfs(grid, r - 1, c); // Up
        dfs(grid, r, c + 1); // Right
        dfs(grid, r, c - 1); // Left
    }
}
<img width="941" height="472" alt="image" src="https://github.com/user-attachments/assets/462ea4b3-ee8a-4203-ad9e-211a9ae7af14" />

