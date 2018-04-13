## Solution

```
public static boolean isStringPalindrome(String str){
    if ((str==null) || (str.length()==0)) return true;
    for(int i=0; i<str.length()/2; i++)
    {
        Character start = str.charAt(i);
        Character end = str.charAt(str.length()-1-i);
        
        if(!start.equals(end))
          return false;
        
    }
    
    return true;
}
```

## Notes
1. null cannot be converted to boolean

2. use length/2 to improve reduce unnecessary computation