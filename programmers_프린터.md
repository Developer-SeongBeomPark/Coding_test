```
import java.util.*;

class Solution {
	class Dictionary{
		int priority;
		int loc_value;
		public Dictionary(int priority, int loc_value) {
			this.priority = priority;
			this.loc_value = loc_value;
		}
	}
	
	
    public int solution(int[] priorities, int location) {
        int answer = 0;
        
        Queue<Dictionary> q = new LinkedList<>();
        for(int i = 0; i < priorities.length; i++) {
        	//Dictionary d = new Dictionary(priorities[i],i);
        	//q.offer(d);
        	q.offer(new Dictionary(priorities[i],i));
        }
        
        while(!q.isEmpty()) {
        	boolean pass = false;
        	for(Dictionary value : q) {
        		if(value.priority > q.peek().priority) {
        			pass = true;
        			break;
        		}
        	}
        	
        	Dictionary dic = q.poll();
        	if(pass) {
        		q.offer(dic);
        	}
        	else {
        		answer++;
        		if(dic.loc_value == location) break;
        	}
        }
        
        return answer;
    }
}
```
