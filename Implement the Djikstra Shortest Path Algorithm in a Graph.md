## Solution

```
public static List<Vertex> getShortestPath(Vertex source, Vertex target) {
    if(source==null||target==null) return null;
    
    //Set<String> set = new HashSet<>();
    PriorityQueue<Vertex> q = new PriorityQueue<>();
    source.minDistance = 0;
    q.add(source);
    
    while(!q.isEmpty())
    {
        Vertex cur = q.remove();
        if(cur==target) break;
        //set.add(cur.name);
        for(Edge e: cur.adjacencies)
        {
            Vertex v = e.target;
            if(v.minDistance > (cur.minDistance+e.weight))
            {
                v.previous = cur;
                v.minDistance = cur.minDistance+e.weight;
                q.add(v);
            }
            // no need to check if v has been visited, as if v is visited, v.minDistance has already minimum
            // if(!set.contains(v.name))
            // {
            //     if(v.minDistance > (cur.minDistance+e.weight))
            //     {
            //       v.previous = cur;
            //       v.minDistance = cur.minDistance+e.weight;
            //     }
            //     q.add(v);
            // }
        }
    }
    
    List<Vertex> list = new ArrayList<>();
    Vertex current = target;
    while(current!=source)
    {
        list.add(current);
        current = current.previous;
    }
    list.add(source);
    Collections.reverse(list);

    // Stack<Vertex> st = new Stack<>();
    // Vertex current = target;
    // while(current!=source)
    // {
    //     st.push(current);
    //     current = current.previous;
    // }
    
    // List<Vertex> list = new ArrayList<>();
    // list.add(source);
    // while(!st.isEmpty())
    // {
    //     Vertex v = st.pop();
    //     list.add(v);
    // }
    
    return list;
}
```

## Notes
1.     class InterComp implements Comparator<Interval>{
        public int compare(Interval a, Interval b)
        {
            return Integer.compare(a.start, b.start);
        }
        
    } 
new PriorityQueue<>(capacity, new InterComp()); or move the InterComp definition inside. new Comparator<Vertex>{public int compare()}

2. Implement a compareTo(Vertex, v) in the Vertex class

3. https://www.youtube.com/watch?v=pVfj6mxhdMw

4. no need to check if v has been visited, as if v is visited, v.minDistance has already reached minimum


