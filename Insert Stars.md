## Solution

```
Given a string, recursively compute a new string where the identical adjacent characters in the original string are separated by a "*".

public static String insertPairStar(String s) {
    if (s==null||s.length()<2) return s;
    
    StringBuilder sb = new StringBuilder();
    for(int i=0; i<s.length()-1; i++)
    {
        Character c1 = s.charAt(i);
        Character c2 = s.charAt(i+1);
        sb.append(c1);
        if(c1.equals(c2))
          sb.append("*");
    }
    
    sb.append(s.charAt(s.length()-1));
    
    return sb.toString();
}
```

## Notes
```
iterative: Don't forget the last element.

recursive solution:
public static String insertPairStar(String s) {
    // Error case
    if (s == null)
      return null;
    // Base case
    else if (s.length() == 1)
      return s;
    // Recursive case for matching
    else if (s.substring(0,1).equals(s.substring(1,2))) {
      return s.substring(0,1) + "*" + insertPairStar(s.substring(1,s.length()));
    }
    // Recursive case for non-matching
    return s.substring(0,1) + insertPairStar(s.substring(1,s.length()));
  }
```
