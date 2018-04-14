## Solution

```
public static boolean isBalanced(String input) {
    if(input==null) return false;
    
    HashMap<String, String> map = new HashMap<>();
    map.put("(", ")");
    map.put("[", "]");
    map.put("{", "}");
    
    Stack<String> st = new Stack<>();

    for(int i=0; i<input.length(); i++)
    {
        String str = input.charAt(i) + "";
        if(map.get(str)!=null)
           st.push(str);
        else
        {
           if(st.isEmpty()) return false;
           String s = st.pop();
           if(!map.get(s).equals(str)) return false;
        }
    }
    
    return st.isEmpty();
}
```

## Notes
Remember to check if st.isEmpty()

