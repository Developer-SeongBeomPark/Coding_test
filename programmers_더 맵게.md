```
import java.util.Arrays;
import java.util.PriorityQueue;

class Solution {
    public int solution(int[] scoville, int K) {
    	Arrays.sort(scoville);
    	if(scoville[0] == 0 && scoville[1] == 0) {
    		return -1;
    	}
    	
    	int count = 0;
    	PriorityQueue<Integer> pq = new PriorityQueue<>();
    	for(int value : scoville) {
    		pq.offer(value);
    	}
    	
    	int min_scoville = pq.peek();
    	while(min_scoville < K) {
    		if(pq.size() > 1) {
    			int a = pq.poll();
        		int b = pq.poll();
        		int mix_scoville = a + 2 * b;
        		pq.add(mix_scoville);
    		}
    		else return -1;
    		
    		count++;
    		min_scoville = pq.peek();
    	}
    	
        return count;
    }
}
```
