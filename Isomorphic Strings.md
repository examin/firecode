## Solution

```
public static boolean isIsomorphic(String input1, String input2) {
    if(input1==null||input2==null) return false;
    if(input1.length()!=input2.length()) return false;
    if(input1.length()==0||input2.length()==0) return true;
    
    Map<Character, ArrayList<Integer>> map1 = toMap(input1);
    Map<Character, ArrayList<Integer>> map2 = toMap(input2);
    
    ArrayList<ArrayList<Integer>> v1 = new ArrayList<>(map1.values());
    ArrayList<ArrayList<Integer>> v2 = new ArrayList<>(map2.values());
    
    if (v1.size()!=v2.size()) return false;
    for(int i=0; i<v1.size(); i++)
    {
        ArrayList<Integer> l1 = v1.get(i);
        ArrayList<Integer> l2 = v2.get(i);
        return samelist(l1,l2);
    }
    
    return true;
}

public static Map<Character, ArrayList<Integer>> toMap(String input1)
  {
    Map<Character, ArrayList<Integer>> map = new LinkedHashMap<>();
    
    for(int i=0; i<input1.length(); i++)
    {
        Character c = input1.charAt(i);
        if(map.get(c)==null)
        {
            ArrayList<Integer> list = new ArrayList<>();
            list.add(i);
            map.put(c, list);
        }else{
            ArrayList<Integer> list = map.get(c);
            list.add(i);
        }
    }
    
    return map;
  }
  
public static boolean samelist(ArrayList<Integer> l1, ArrayList<Integer> l2)
  {
      if(l1.size()!=l2.size()) return false;
      for(int i=0; i<l1.size(); i++)
      {
          if(!l1.get(i).equals(l2.get(i)))
             return false;
      }
      return true;
  }
```

## Notes
// check the frequency from the beginning to make sure the order is correct

if(input1.length() != input2.length()) return false;
    else {
        HashMap<Character, Integer> hm1 = new HashMap<>();
        HashMap<Character, Integer> hm2 = new HashMap<>();
        for(int i=0; i < input1.length(); i++){
            Character c1 = input1.charAt(i);
            Integer val1 = hm1.get(c1) == null ? 1 : hm1.get(c1) + 1;
            hm1.put(c1,val1);
        
            Character c2 = input2.charAt(i);
            Integer val2 = hm2.get(c2) == null ? 1 : hm2.get(c2) + 1;
            hm2.put(c2,val2);
            
            if(!hm1.get(c1).equals(hm2.get(c2))) return false;
        }
        return true;
    }
 This solution is wrong. Check out leetcode: https://leetcode.com/problems/isomorphic-strings/description/   
