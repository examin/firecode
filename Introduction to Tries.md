## Solution

```
class TrieNode {
    Character c;
    Boolean isLeaf = false;
    HashMap<Character, TrieNode> children = new HashMap<>();
    public TrieNode() {}
    public TrieNode(Character c) {
        this.c = c;
    }
}

class Trie {
    private TrieNode root;
    
    // Implement these methods : 
    public Trie() {
        root = new TrieNode();
    }
    public void insertWord(String word) {
        if(word==null||word.length()==0) return;
        TrieNode cur = root;
        HashMap<Character, TrieNode> children = cur.children;
        for(int i=0; i<word.length(); i++)
        {
            char c = word.charAt(i);
            if(children.containsKey(c))
            {
                cur = children.get(c);
            }else{
                TrieNode n = new TrieNode(c);
                children.put(c,n);
                cur = n;
            }
            children = cur.children;
            
            if(i==word.length()-1) cur.isLeaf = true;
        }
    }
    public Boolean searchWord(String word) {
        TrieNode cur = root;
        HashMap<Character, TrieNode> children = cur.children;
        for(int i=0; i<word.length(); i++)
        {
            char c = word.charAt(i);
            if(children.containsKey(c))
            {
                cur = children.get(c);
                children = cur.children;
            }else{
                return false;
            }
        }
        return cur.isLeaf;
    }
    public Boolean searchPrefix(String word) {
        TrieNode cur = root;
        HashMap<Character, TrieNode> children = cur.children;
        for(int i=0; i<word.length(); i++)
        {
            char c = word.charAt(i);
            if(children.containsKey(c))
            {
                cur = children.get(c);
                children = cur.children;
            }else{
                return false;
            }
        }
        return true;
    }
}
```

## Notes
With a Trie, search complexities can be reduced to O(k) where k is the key or word length.

