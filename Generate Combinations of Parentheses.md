## Solution

```
Write a method to return all valid combinations of n-pairs of parentheses.

The method should return an ArrayList of strings, in which each string represents a valid combination of parentheses.

The order of the strings in the ArrayList does not matter.


public static ArrayList<String> combParenthesis(int pairs) {
    ArrayList<String> list = new ArrayList<String>();
    permute(pairs, pairs, "", list);
    return list;
}

public static void permute(int left, int right, String str, ArrayList<String> list) {
    if(left==0&&left==right)
    {
        list.add(str);
        return;
    }
    
    if(left<=right&&left>=0)
    {
        permute(left-1, right, str+"(", list);
        permute(left, right-1, str+")", list);
    }
}
```

## Notes
Key: in the remaining part, the # of left has to be less than or equal to right. Permutation problem (recursion)
0.http://blog.gainlo.co/index.php/2016/12/23/uber-interview-questions-permutations-parentheses/?utm_source=comment&utm_campaign=comment&utm_medium=122216
1. https://www.youtube.com/watch?v=WHR1trMsvOE&t=516s
2. https://leetcode.com/problems/permutations/description/
3. https://leetcode.com/problems/valid-parentheses/description/
