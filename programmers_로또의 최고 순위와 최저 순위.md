```
class Solution {
    public int[] solution(int[] lottos, int[] win_nums) {
        int[] answer = new int[2];
        int max = 0;
        int min = 0;
        
        for(int lottos_value : lottos) {
        	if(lottos_value == 0) {
        		max++;
        		continue;
        	}
        	for(int win_nums_value : win_nums) {
        		if(lottos_value == win_nums_value) {
        			max++;
        			min++;
        			break;
        		}
        	}
        }
        
        if(max < 2) {
        	answer[0] = 6;
        }
        else {
        	answer[0] = 7 - max;
        }
        
        if(min < 2) {
        	answer[1] = 6;
        }
        else {
        	answer[1] = 7 - min;
        }
        
        
        return answer;
    }
}
```
