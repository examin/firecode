## Solution

```
public static ArrayList<Interval> insertRange(ArrayList<Interval> intervalsList, Interval insert) {
    if(insert==null) return intervalsList;
    if(intervalsList==null) 
    {
        intervalsList = new ArrayList<Interval>();
        intervalsList.add(insert);
        return intervalsList;
    }
    if(intervalsList.size()==0) 
    {
        intervalsList.add(insert);
        return intervalsList;
    }
    
    ArrayList<Interval> list = new ArrayList<>();
    for(int i=0; i<intervalsList.size(); i++)
    {
        Interval a = intervalsList.get(i);
        if(insert.start>a.end)
           list.add(a);
        else if(insert.end<a.start)
        {
           list.add(insert);
           insert = null;
           list.add(a);
        }
        else
           insert = merge(insert, a);
    }
    
    if(insert!=null) list.add(insert);
    
    return list;
    
}

public static Interval merge(Interval a, Interval b)
{
    return new Interval(Math.min(a.start, b.start), Math.max(a.end, b.end));
}
```

## Notes
1. Make sure to check whether a the last insert is null or not.
2. Cross compare start with end
