# Intuition
You can add everytime you see a value of 1 and if the neighbour is also 1 substract 2 and there you go the result is ready. But you've used two for loops.

# Approach
DFS seemed a good catch here. Also it is similar question number 79. So the solution is like everytime you catch a value of 1 add 1 for every 0 valued neighbour. If you wonder what if the neighbour is visited already.. I change the value to be -1  for every visited cell.

# Complexity
- Time complexity:
 $$O(n)$$ -->n

- Space complexity:
 $$O(n)$$ -->n

# Code
```
class Solution {
    public int islandPerimeter(int[][] grid) {
        int row = grid.length;
        int column = grid[0].length;


        for(int i=0;i<row;i++){
            for(int j=0;j<column;j++){
                if(grid[i][j]==1)
                return dfs(i,j,grid);
            }
        }
        return 0;
    }
    public int dfs(int i,int j,int[][] grid){
        if(i>=grid.length || i<0 || j>=grid[0].length || j<0 || grid[i][j] == 0) return 1;
        if (grid[i][j] == -1) return 0; //visited
        grid[i][j] = -1;
        return dfs(i+1,j,grid)+dfs(i-1,j,grid)+dfs(i,j+1,grid)+dfs(i,j-1,grid);
    }
}

```