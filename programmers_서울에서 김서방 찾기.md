```
import java.util.Arrays;

class Solution {
    public String solution(String[] seoul) {
        int idx = 0;
		for(int i = 0; i < seoul.length; i++) {
			if(seoul[i].equals("Kim")) {
				idx = i;
				break;
			}
		}
    /*
    for문 대체:
    int idx = Arrays.asList(seoul).indexOf("Kim");
    */
		
        String answer = "김서방은 " + String.valueOf(idx) + "에 있다";
        return answer;
    }
}
```
