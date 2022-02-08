```
import java.util.*;

class Solution {
    public int solution(String[][] clothes) {
    	int answer = 1;
    	Set<String> hs = new HashSet<>();
    	for(int i = 0; i < clothes.length; i++) {
    		hs.add(clothes[i][1]);
    	}
    	
    	for(String value : hs) {
    		int count = 1;
    		for(int i = 0; i < clothes.length; i++) {
    			if(value.equals(clothes[i][1])) count++;
    		}
    		answer *= count;
    	}
     
        return answer - 1;
    }
}
```
