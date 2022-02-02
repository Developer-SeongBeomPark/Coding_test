```
import java.util.ArrayList;
import java.util.List;

class Solution {
    public int[] solution(int[] answers) {
    	int[][] answer_arr = {
    			{1,2,3,4,5},
    			{2,1,2,3,2,4,2,5},
    			{3,3,1,1,2,2,4,4,5,5}
    	};
    	int[] count = {0,0,0};
    	
    	for(int i = 0; i < 3; i++) {
    		for(int j = 0; j < answers.length; j++) {
    			if(answers[j] == answer_arr[i][j % (answer_arr[i].length)]) {
    				count[i]++;
    			}
    		}
    	}
    	int max_count = Math.max(count[0], Math.max(count[1], count[2]));
    	List<Integer> list = new ArrayList<>();
    	for(int i = 0; i < 3; i++) {
    		if(count[i] == max_count) list.add(i+1);
    	}
    	
    	int[] answer = new int[list.size()];
    	for(int i = 0; i < list.size(); i++) {
    		answer[i] = list.get(i);
    	}
        
        return answer;
    }
}
```
