```
import java.util.*;

class Solution {
    public int solution(int[] citations) {
        int h_index = 0;
        List<Integer> list = new ArrayList<>();
        for(int value : citations) {
        	list.add(value);
        }
        Collections.sort(list,Collections.reverseOrder());
        
        for(int i = 0; i < list.size(); i++) {
        	if(list.get(i) >= i+1) {
        		h_index = Math.max(h_index, i+1);
        	}
        }
        
        
        return h_index;
    }
}
```
