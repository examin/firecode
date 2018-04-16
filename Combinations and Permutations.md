## Solution

```
Given a string, list all possible combinations and permutations of its characters.

public static ArrayList<String> getCombPerms(String s) {
    ArrayList<String> list = new ArrayList<>();
    if(s==null) return null;
    if(s.length()==0) return list;

    //getPerms(list, "", s); 
    getCombs(list, "", s, 0);
    ArrayList<String> com_list = new ArrayList<>(list);
    for(String str:com_list)
    {
        getPerms(list, "", str, str);
    }
    
    return list;
}

public static void getPerms(ArrayList<String> list, String prefix, String remaining, String s) {
    if(remaining.equals("")) 
    {
        if(!prefix.equals(s)) list.add(prefix);
        return;
    }
    
    for(int i=0; i<remaining.length();i++)
    {
        String new_prefix = prefix+remaining.substring(i, i+1);
        String new_remaining = remaining.substring(0,i) + remaining.substring(i+1);
        getPerms(list, new_prefix, new_remaining, s); 
    }
}

public static void getCombs(ArrayList<String> list, String str, String s, int k) {
    if(k==s.length()) 
    {
        if(!str.equals("")) list.add(str);
        return;
    }
    
    getCombs(list, str+s.charAt(k), s, k+1);
    getCombs(list, str, s, k+1);
}
```

## Notes

