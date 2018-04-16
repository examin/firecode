## Solution

```
public static  ArrayList<String> getStringsFromNums(String digits) {
    ArrayList<String> list = new ArrayList<>();
    if(digits==null) return null;
    if(digits.length()==0) return list;
    
    HashMap<String, String> map = new HashMap<>();
    map.put("2", "abc");
    map.put("3", "def");
    map.put("4", "ghi");
    map.put("5", "jkl");
    map.put("6", "mno");
    map.put("7", "pqrs");
    map.put("8", "tuv");
    map.put("9", "wxyz");
    
    helper(digits, "", 0, list, map);
    
    return list;
}

public static void helper(String digits, String str, int index, ArrayList<String> list, HashMap<String, String> map)
{
    if(index==digits.length())
    {
       list.add(str);
       return; 
    }
    if(index>digits.length()) 
       return;
    
    String vals = map.get(digits.charAt(index)+"");
    for(int i=0; i<vals.length(); i++)
    {
        helper(digits, str+vals.charAt(i), index+1, list, map);
    }
}
```

## Notes

