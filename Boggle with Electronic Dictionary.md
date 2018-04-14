## Solution

```
public ArrayList<String> boggleSearchWithDict(char[][] board, Trie dictionary){
    TreeSet<String> set = new TreeSet<>();
    if(board==null||board.length==0) return new ArrayList<>(set);
    int rows = board.length;
    int cols = board[0].length;
    boolean[][] visited = new boolean[rows][cols];
    for(int i=0; i<rows; i++)
    {
        for(int j=0; j<cols; j++)
        {
            helper(board, i, j, set, dictionary, visited, "");
        }
    }
    
    return new ArrayList<>(set);
}

public void helper(char[][] board, int row, int col, TreeSet<String> set, Trie dict, boolean[][] visited, String str)
{
    if(!dict.searchPrefix(str)) 
      return;
    
    if(dict.searchWord(str))
    {
        set.add(str);
        //return;
    }
    
    int rows = board.length;
    int cols = board[0].length;
    if(row<0||col<0||row>=rows||col>=cols) return;
    
    visited[row][col] = true;
    helper(board, row-1, col, set, dict, visited, str+board[row][col]);
    helper(board, row, col-1, set, dict, visited, str+board[row][col]);
    helper(board, row+1, col, set, dict, visited, str+board[row][col]);
    helper(board, row, col+1, set, dict, visited, str+board[row][col]);
    visited[row][col] = false;
}
```

## Notes
TreeSet is automatically sorted and unique
