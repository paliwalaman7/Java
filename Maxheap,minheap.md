=>Max heap concepts -->
       
       // Priority queue to store the improvement in descending order(max heap)
        PriorityQueue<double[]> maxHeap = new PriorityQueue<>((a, b) -> Double.compare(b[0], a[0]));

       // Priority queue to store the improvement in ascending order(min heap)
        PriorityQueue<double[]> maxHeap = new PriorityQueue<>((a, b) -> Double.compare(a[0], b[0]));

       // Priority queue to store the improvement in ascending order in a[0],and if a,b is equal,choose only priority which have small index..
          PriorityQueue<double[]> maxHeap = new PriorityQueue<>((a, b) -> {
            if(a[0]==b[0]) return Double.compare(a[1],b[1]);
            else return Double.comapre(a[0],b[0]);
          }); 

      //min heap
      PriorityQueue<Integer> minHeap = new PriorityQueue<>();

      //max heap
      PriorityQueue<Integer> maxHeap = new PriorityQueue<>(collections.reverseOrder());

      //TreeSet ??? 
        
