## Solution

```
public boolean breadthFirstSearch(Node rootNode, String data){
    if(rootNode==null) return false;
    
    Queue<Node> q = new LinkedList<>();
    q.add(rootNode);
    while(!q.isEmpty())
    {
        Node n = q.remove();
        n.visited = true;
        if(n.data == data) return true;
        for(Node node:n.adjacentNodes)
        {
            if(!node.visited)
               q.add(node);
        }
    }
    
    return false;
}

```

## Notes
