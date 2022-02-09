```
class Solution {
    public int[] solution(int brown, int yellow) {
        int[] answer = new int[2];
        
        int x = 0, y = 0;
        if(yellow == 1) {
        	answer[0] = 3;
        	answer[1] = 3;
        	return answer;
        }
        
        for(int i = 1; i < yellow; i++) {
        	if(yellow % i == 0) {
        		x = i;
        		y = yellow / i;
        		if(2*(x + y + 2) == brown) {
        			answer[0] = y + 2;
        			answer[1] = x + 2;
        			break;
        		}
        	}
        }
        
        return answer;
    }
}
```
