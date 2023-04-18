
# Code
```
class Solution {
    int row, column;
    boolean[][] visited;
    public boolean exist(char[][] board, String word) {
        row = board.length;
        column = board[0].length;
        visited = new boolean[row][column];

        for(int i=0;i<row;i++){
            for(int j=0;j<column;j++){
                if(board[i][j] == word.charAt(0) && checkNeighbour(word, board, 0, i, j)) return true;
            }
        }
        return false;
    }

    public boolean checkNeighbour(String word, char[][] board, int index, int x, int y){


        if(x >= row || x < 0 || y >= column || y < 0 ) return false; // bound check
        if(board[x][y] != word.charAt(index)) return false; // not a match
        if(visited[x][y]) return false; // already visited

        if(index == word.length() - 1) return true;
        
        visited[x][y] = true;
        index++;

        if( checkNeighbour(word, board, index, x+1, y)||
            checkNeighbour(word, board, index, x-1, y)||
            checkNeighbour(word, board, index, x, y+1)||
            checkNeighbour(word, board, index, x, y-1)  ) return true;

        visited[x][y] = false; // curr unvisited
        
        return false;
    }
}
```