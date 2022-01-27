```
class Solution {
    boolean solution(String s) {
    	int p_count = 0, y_count = 0;
    	boolean answer = true;
    	
    	for(int i = 0; i < s.length(); i++) {
    		if(s.charAt(i) == 'p' || s.charAt(i) == 'P') p_count++;
    		else if(s.charAt(i) == 'y' || s.charAt(i) == 'Y') y_count++;
    	}
    	
    	if(p_count == y_count) return answer;
        

        // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
        System.out.println("Hello Java");

        return !answer;
    }
}
```
