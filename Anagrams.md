## Solution

```
public static boolean isAnagram(String input1, String input2) {
    if(input1==null||input2==null) return false;
    if(input1.length()!=input2.length()) return false;
    
    //this is in fact linear space too, because the key won't be more than 26.
    Map<Character, Integer> map1 = new HashMap<Character, Integer>();
    Map<Character, Integer> map2 = new HashMap<Character, Integer>();

    for(int i=0; i<input1.length(); i++)
    {
        Character c = input1.charAt(i);
        if(map1.get(c)==null)
           map1.put(c, 1);
        else
        {
           int count = map1.get(c);
           map1.put(c, count+1);
        }
        
        Character c2 = input2.charAt(i);
        if(map2.get(c2)==null)
           map2.put(c2, 1);
        else
        {
           int count = map2.get(c2);
           map2.put(c2, count+1);
        }
    }
    
    for(Map.Entry<Character, Integer> entry:map1.entrySet())
    {
        Character c = entry.getKey();
        int val = entry.getValue();
        if(map2.get(c)!=val)
           return false;
    }
    
    return true;
    
}
```

## Notes
public static boolean isAnagram(String input1, String input2) {
    if(input1 == null || input2 == null || (input1.length() != input2.length())){
        return false;
    } else {
        int[] buffer = new int[26];
        for(int i=0; i < input1.length(); i++){
            buffer[input1.charAt(i) - 'a']++;
            buffer[input2.charAt(i) - 'a']--;
        }
        for(int j=0; j < buffer.length; j++){
            if(buffer[j] != 0) return false;
        }
        return true;
    }
}
