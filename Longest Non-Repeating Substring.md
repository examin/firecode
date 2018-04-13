## Solution

```
public static int longestNRSubstringLen(String input) {
    if(input==null || input.length()==0) return 0;
    
    Set<Character> set = new HashSet<>();
    
    int i=0, j =0, max = 0;
    int l = input.length();
    while(i<l&&j<l)
    {
        Character c = input.charAt(j);
        if(!set.contains(c))
        {
            set.add(c);
            j++;
            max = Math.max(max, j-i);
        }
        else
        {
            set.remove(input.charAt(i));
            i++;
        }
            
    }
    
    return max;
}
```

## Notes
https://leetcode.com/articles/longest-substring-without-repeating-characters/

public int lengthOfLongestSubstring(String s) {
        int n = s.length(), ans = 0;
        Map<Character, Integer> map = new HashMap<>(); // current index of character
        // try to extend the range [i, j]
        for (int j = 0, i = 0; j < n; j++) {
            if (map.containsKey(s.charAt(j))) {
                i = Math.max(map.get(s.charAt(j)), i);
            }
            ans = Math.max(ans, j - i + 1);
            map.put(s.charAt(j), j + 1);
        }
        return ans;
    }