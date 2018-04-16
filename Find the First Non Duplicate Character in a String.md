## Solution

```
public static Character firstNonRepeatedCharacter(String str) {
    if((str==null) || (str.length()==0)) return null;
    
    Map<Character, Integer> map = new LinkedHashMap<>();
    
    for(int i=0; i<str.length();i++)
    {
        Character c = str.charAt(i);
        if(map.get(c)==null)
          map.put(c, 1);
        else{
            int count = map.get(c);
            map.put(c, count+1);
        }
    }
    
    for(Map.Entry<Character, Integer> entry:map.entrySet())
    {
        Character key = entry.getKey();
        Integer value = entry.getValue();
        if(value==1)
           return key;
    }
    
    return null;   
}
```

## Notes

