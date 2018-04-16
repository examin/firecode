## Solution

```
You're given a 2D board which contains an m x n matrix of chars - char[][] board. Write a method - printPaths that prints all possible paths from the top left cell to the bottom right cell. Your method should return an ArrayList of Strings, where each String represents a path with characters appended in the order of movement. You're only allowed to move down and right on the board. The order of String insertion in the ArrayList does not matter.
 
public ArrayList<String> printPaths(char[][] board){
    if(board==null || board.length==0) return null;
    ArrayList<String> list = new ArrayList<String>();
    StringBuilder sb = new StringBuilder();
    int rows = board.length;
    int cols = board[0].length;
    if(cols!=0) helper(board, list, sb, 0, 0, cols-1, rows-1);
    
    return list;
}

public void helper(char[][] board, ArrayList<String> list, StringBuilder sb, int x1, int y1, int x2, int y2)
{
    sb.append(board[y1][x1]);
    if(x1==x2 && y1==y2) 
    {
        list.add(sb.toString());
        return;
    }
    
    if(x1<x2)
    {
       StringBuilder new_sb_1 = new StringBuilder(sb);
       helper(board, list, new_sb_1, x1+1, y1, x2, y2);
    }
    
    if(y1<y2)
    {
       StringBuilder new_sb_2 = new StringBuilder(sb); 
       helper(board, list, new_sb_2, x1, y1+1, x2, y2);
    }
    

}

```

## Notes
Since strings are immutable
String s = "hello";
    String backup_of_s = s;
    s = "bye";
    
Cannot do this web StringBuilder
    
It is a subset problem