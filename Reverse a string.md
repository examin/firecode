## Solution

```
Write a method that takes in a String and returns the reversed version of the String. 

public static String reverseString(String str){
    String inputString = str;
    String outputString = null;
    StringBuilder sb = new StringBuilder();
    
    if (str==null) return null;
    if (str.length()==0) return "";
    for(int i=str.length()-1; i>=0; i--)
    {
        sb.append(String.valueOf(str.charAt(i)));
    }
    
    outputString = sb.toString();
    
    return outputString;
}

```

## Notes
when use i--, make sure i>=0
