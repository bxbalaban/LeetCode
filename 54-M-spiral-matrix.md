
# Code
```
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {

        List<Integer> result = new ArrayList();

        int columnEnd = matrix[0].length-1;
        int columnBegin = 0;
        int rowEnd = matrix.length-1;
        int rowBegin = 0;

        while(columnBegin <= columnEnd && rowBegin <= rowEnd){
            //#1 traverse right
            for(int i = columnBegin ; i <= columnEnd ; i++){
                result.add(matrix[rowBegin][i]);
            }
            rowBegin++;

            //#2 traverse down
            for(int i = rowBegin ; i <= rowEnd ; i++){
                result.add(matrix[i][columnEnd]);
            }
            columnEnd--;

            //#3 traverse left
            if(rowBegin <= rowEnd){
                for(int i = columnEnd ; i >= columnBegin ; i--){
                    result.add(matrix[rowEnd][i]);
                }
            }
            rowEnd--;

            //#4 traverse up
            if(columnBegin <= columnEnd){
                for(int i = rowEnd ; i >= rowBegin ; i--){
                    result.add(matrix[i][columnBegin]);
                }
            }
            columnBegin++;

        }

        return result;        
    }

}
```