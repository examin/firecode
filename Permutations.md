## Solution

```
public static boolean permutation(String str1, String str2) {
    if(str1==null || str2==null) return false;
    if(str1.length()!=str2.length()) return false;
    
    Map<Character, Integer> map1 = helper(str1);
    Map<Character, Integer> map2 = helper(str2);

    for(Map.Entry<Character, Integer> entry: map1.entrySet())
    {
        Character key = entry.getKey();
        int val = entry.getValue();
        if(map2.get(key) == null || map2.get(key)!=val) return false;
    }
    
    return true;
}

public static Map<Character, Integer> helper(String str)
{
    Map<Character, Integer> map = new HashMap<Character, Integer>();
    for(int i=0; i<str.length(); i++)
    {
        Character c = str.charAt(i);
        if(map.get(c) == null) 
          map.put(c, 1);
        else{
          int count = map.get(c);
          map.put(c, count+1);
        }
    }
    return map;
}
```

## Notes
```
public static boolean permutation(String str1, String str2) {
  if (str1.length() != str2.length()) {
      return false;
  }
      
  int[] letters = new int[256];
  char[] str1_arr = str1.toCharArray();
  // Record all the characters which are in the first string.
  for (char c : str1_arr) {
      letters[c]++;
  }
  // Remove all the characters of second string from records.
  for (int i=0; i<str2.length(); i++) {
      int c = (int) str2.charAt(i);
      // If any character is not found or found more than the number of times 
      // in the second string, strings are not permutation of each other 
      if (--letters[c] < 0) {
          return false;
      }
  }
  return true;
}
```
