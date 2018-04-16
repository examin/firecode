## Solution

```
public static ArrayList<String> getPermutations(String s) {
    ArrayList<String> list = new ArrayList<>();
    if(s==null) return null;
    if(s.length()==0) return list;

    helper("", s, list);
    
    return list;
}

public static void helper(String prefix, String remaining, ArrayList list)
{
    //if(prefix.length()==s.length())
    if(remaining.equals(""))
    {
        list.add(prefix);
        return;
    }
    
    for(int i=0; i<remaining.length(); i++)
    {
        helper(prefix+remaining.substring(i, i+1), 
        remaining.substring(0,i)+remaining.substring(i+1), 
        list);
    }
}
```

## Notes

