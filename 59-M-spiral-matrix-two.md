# Intuition
linear 

# Approach
there are 4 different movement style. We implement each accordingly.

# Complexity
- Time complexity:
 $$O(n)$$ --> n^2


# Code
```
class Solution {
    public int[][] generateMatrix(int n) {
        int matrix[][] = new int[n][n];
        int count = 1;
        
        int columnBegin = 0;
        int columnEnd = n-1;
        int rowBegin = 0;
        int rowEnd = n-1;

        while(rowBegin <= rowEnd && columnBegin <= columnEnd){
            //#1 right 
            for(int i=columnBegin; i<=columnEnd; i++){
                matrix[rowBegin][i] = count;
                count++;
            }
            rowBegin++;

            //#2 down
            for(int i=rowBegin; i<=rowEnd; i++){
                matrix[i][columnEnd] = count;
                count++;
            }
            columnEnd--;
            
            //#3 left
            if(rowBegin <= rowEnd){
                for(int i=columnEnd; i>=columnBegin; i--){
                    matrix[rowEnd][i] = count;
                    count++;
                }
                rowEnd--;
            }

            //#3 up
            if(columnBegin <= columnEnd){
                for(int i=rowEnd; i>=rowBegin; i--){
                    matrix[i][columnBegin] = count;
                    count++;
                }
                columnBegin++;
            }

        }
        
        return matrix;
    }
}
```