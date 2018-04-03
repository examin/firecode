## Solution

```
public boolean depthFirstSearch(Node rootNode, String data){
    if(rootNode==null) return false;
    
    if(!rootNode.visited)
    {
        if(rootNode.data==data) return true;
        rootNode.visited = true;
        for(Node n: rootNode.adjacentNodes)
        {
           if(depthFirstSearch(n, data))
              return true;
        }
    }
    return false;
}
```

## Notes
public boolean depthFirstSearch(Node rootNode, String data) {
    Stack<Node> s = new Stack<Node>();
    s.add(rootNode);
    rootNode.visited = true;
    while(!s.isEmpty()){
        Node n = s.pop();
        if(n.data != null && n.data.equals(data)) {
            return true;
        }
        for(Node adj : n.adjacentNodes){
            if(!adj.visited){
                    adj.visited = true;
                    s.push(adj);
            }
        }
    }              
    return false;
}
