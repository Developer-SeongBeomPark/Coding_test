```
class Solution {
	public boolean solution(int x) {
		boolean answer = true;
        String int_to_str = String.valueOf(x);
        int len = int_to_str.length();
        int sum = 0;
        String str[] = int_to_str.split("");
        
        for(int i = 0; i < len; i++) {
        	sum += Integer.parseInt(str[i]);
        }

        if(x % sum == 0) {
        	return answer;
        }


        
        return !answer;
    }
}
```
