```
class Solution {
    public String solution(String s) {
        String answer = "";
        int max_value = Integer.MIN_VALUE;
        int min_value = Integer.MAX_VALUE;
        String[] arr = s.split(" ");
        
        for(int i = 0; i < arr.length; i++) {
        	int value = Integer.parseInt(arr[i]);
        	if(value > max_value) {
        		max_value = value;
        	}
        	if(value < min_value) {
        		min_value = value;
        	}
        }
        answer += String.valueOf(min_value) + " " + String.valueOf(max_value);
        return answer;
    }
}
```
