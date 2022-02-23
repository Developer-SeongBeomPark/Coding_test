```
class Solution {
    public int solution(int n) {
        int answer = 0;
        String str = "";
        
        while(n > 0) {
        	int x = n % 3;
        	n = n / 3;
        	str = str.concat(String.valueOf(x));
        }
        
        for(int i = 0; i < str.length(); i++) {
        	int s = str.charAt(i) - 48;
        	answer += s * Math.pow(3, str.length()-1-i);
        }
        
        
        return answer;
    }
}
```
