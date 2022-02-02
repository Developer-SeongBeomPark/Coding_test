```
import java.util.*;

class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
    	int order = 0;
    	List<Integer> answer_list = new ArrayList<>();
    	while(order < speeds.length) {
    		int count = 0;
    		for(int i = order; i < speeds.length; i++) {
    			progresses[i] += speeds[i];
    		}
    		if(progresses[order] >= 100) {
	    		while(progresses[order] >= 100) {
	    			count++;
	    			order++;
	    			if(order >= speeds.length) break;
	    		}
	    		answer_list.add(count);
    		}
    	}
    	
        int[] answer = new int[answer_list.size()];
        for(int i = 0; i < answer_list.size(); i++) {
        	answer[i] = answer_list.get(i);
        }
        return answer;
    }
}
```
