

# Approach
two for loops and a new array

# Complexity
- Time complexity: $$O(n)$$ --> n^2


# Code
```
class Solution {
    public int[][] transpose(int[][] matrix) {
        int x = matrix.length;
        int y = matrix[0].length;

        int [][] arr = new int [y][x];
        for(int i=0; i<y; i++){
            for(int j=0; j<x ;j++){
                arr[i][j]=matrix[j][i];
            }
        }
        return arr;
    }
}
```