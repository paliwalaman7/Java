=>  
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





     
