# Intuition
```
public boolean searchMatrix(int[][] matrix, int target) {
        boolean flag = false;
        for(int i=0;i<matrix.length;i++){
            if(matrix[i][0] <= target && matrix[i][matrix[i].length-1] >= target){
                for(int j=0;j<matrix[i].length;j++){
                    if(target == matrix[i][j]) flag = true;
                }
            }
        }
        return flag;
    } 
}
```

# Approach
Binary Search and mid/column , mid%column is important

# Complexity
- Time complexity:
$$O(n)$$ --> log(n^2)


# Code
```
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        if(matrix.length == 0) return false;
        int row = matrix.length;
        int column = matrix[0].length;

        int left = 0;
        int right = row * column -1;

        while(left <= right){
            int mid = (left + right) / 2 ;
            int val = matrix[mid/column][mid%column];
            if(val > target){
                right = mid -1;
            }
            else if(val < target){
                left = mid + 1;
            }
            else{
                return true;
            }
        }
        return false;
    }
    
```