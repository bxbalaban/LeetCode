# Intuition
We've seen a similar question on number 79. 

# Approach
We need to dive into the function check here because the main function is pretty straight forward. In check 
*you need to look if the bounds are in correct podition else return 0.
*look for the grid value if it is 0 return 0
*look if the cell already visited before if yes return 0

*if else check the cell visited
*and add +1 then recursively check the other edges in the same way


# Code
```
class Solution {
    boolean visited[][];
    public int maxAreaOfIsland(int[][] grid) {
        visited = new boolean[grid.length][grid[0].length];
        int max = 0;
        for(int i=0;i<grid.length;i++){
            for(int j=0; j<grid[0].length;j++){
                if(grid[i][j] == 1){
                    max = Math.max(max,check(i,j,grid));
                }
            }
        }
        return max;
    }
    public int check(int i,int j,int [][] grid){
        if(i >= grid.length || j >= grid[0].length || i<0 || j<0 || visited[i][j] || grid[i][j] == 0) return 0;
                
        visited[i][j] = true;

        return (1 + check(i+1,j,grid) + check(i-1,j,grid) + check(i,j+1,grid) + check(i,j-1,grid));
    }
}
```