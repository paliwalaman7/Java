``` 
    //order map in java is TreeMap in java...
    TreeMap<Integer, Integer> map = new TreeMap<>();

    //putting method same as map
     map.put(a, map.getOrDefault(a, 0) + 1);  

     //wants to get value of a
     map.get(a);

   
    //TreeMap
     map.firstKey()
     example::
     import java.util.TreeMap;

     public class Main {
     public static void main(String[] args) {
        // Create a TreeMap and populate it with some key-value pairs
        TreeMap<Integer, Integer> map = new TreeMap<>();
        map.put(10, 100);
        map.put(20, 200);
        map.put(30, 300);
        map.put(40, 400);

        // Get the first and last values
        int firstValue = map.get(map.firstKey());
        int lastValue = map.get(map.lastKey());

        // Calculate the difference between the last and first values
        int difference = lastValue - firstValue;

        System.out.println("First value: " + firstValue);
        System.out.println("Last value: " + lastValue);
        System.out.println("Difference between lastValue and firstValue: " + difference);
    }
}

//remove a in map 
 map.remove(a);

```

```
class Solution {
    public int BFS(int start, Map<Integer, List<Integer>> adj, boolean[] visited) {
        Queue<int[]> queue = new LinkedList<>(); // {node, path length}
        queue.add(new int[]{start, 0});
        int maxDistance = 0;

        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int currNode = current[0];
            int dist = current[1];

            for (int neighbor : adj.getOrDefault(currNode, new ArrayList<>())) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.add(new int[]{neighbor, dist + 1});
                    maxDistance = Math.max(maxDistance, dist + 1);
                }
            }
        }

        return maxDistance;
    }

    public int maximumInvitations(int[] favorite) {
        int n = favorite.length;
        Map<Integer, List<Integer>> adj = new HashMap<>();

        // Build reversed graph
        for (int i = 0; i < n; i++) {
            int u = i;
            int v = favorite[i];
            adj.computeIfAbsent(v, k -> new ArrayList<>()).add(u);
        }

        int longestCycleEmplCount = 0;
        int happyCoupleEmplCount = 0;

        boolean[] visited = new boolean[n];

        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                Map<Integer, Integer> mp = new HashMap<>();
                int currNode = i;
                int currNodeCount = 0;

                while (!visited[currNode]) { // Until cycle is not detected
                    visited[currNode] = true;
                    mp.put(currNode, currNodeCount);

                    int nextNode = favorite[currNode]; // Favorite node of currNode
                    currNodeCount++;

                    if (mp.containsKey(nextNode)) { // Cycle detected
                        int cycleLength = currNodeCount - mp.get(nextNode);
                        longestCycleEmplCount = Math.max(longestCycleEmplCount, cycleLength);

                        if (cycleLength == 2) { // Happy couple case
                            boolean[] visitedNodes = new boolean[n];
                            visitedNodes[currNode] = true;
                            visitedNodes[nextNode] = true;
                            happyCoupleEmplCount += 2 + BFS(currNode, adj, visitedNodes) + BFS(nextNode, adj, visitedNodes);
                        }
                        break;
                    }
                    currNode = nextNode;
                }
            }
        }

        return Math.max(happyCoupleEmplCount, longestCycleEmplCount);
    }
}
```

```
prereqMap.get(neighbour).addAll(prereqMap.getOrDefault(node,new HashSet<>())); //addAll
ans.add(prereqMap.getOrDefault(des,new HashSet<>()).contains(src)); //true,false through contains..
```



     
