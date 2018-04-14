## Solution

```
public static ArrayList<String> generateIPAddrs(String s) {
    ArrayList<String> list = new ArrayList<>();
    if(s==null||s.length()==0) return list;
    helper(list, "", s, 0);
    return list;

}

public static void helper(ArrayList<String> list, String prefix, String remaining, int k) {
    if(remaining.length()==0&&k==4) 
    {
        list.add(prefix.substring(1));
        return;
    }
    
    if(remaining.length()==0||k==4)
       return;
    
    for(int i=0; i < remaining.length()&& i<=2; i++)
    {
        String part = remaining.substring(0, i+1);
        if(Integer.valueOf(part)<=255)
        {
           //prefix = prefix + "." + part;
           //remaining = remaining.substring(i+1);
           helper(list, prefix + "." + part, remaining.substring(i+1), k+1);
        }
    } 
}
```

## Notes
1. Avoid changing prefix and remaining at different i (line 27&28)
2. Avoid part gets greater than the maximum integer value
3. Use recursion!!

https://leetcode.com/problems/restore-ip-addresses/discuss/30949/My-code-in-Java
