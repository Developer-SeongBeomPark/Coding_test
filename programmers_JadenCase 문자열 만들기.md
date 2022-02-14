```
class Solution {
    public String solution(String s) {
        String answer = "";
        StringBuilder sb = new StringBuilder();
        
        String[] arr = s.toLowerCase().split("");
        for(int i = 0; i < arr.length; i++) {
        	if(i == 0) arr[i] = arr[i].toUpperCase();
        	else {
        		if(arr[i-1].equals(" ") && !arr[i].equals(" ")) {
        			arr[i] = arr[i].toUpperCase();
        		}
        	}
        	sb.append(arr[i]);
        }
        
        answer = sb.toString();

        return answer;
    }
}
```
