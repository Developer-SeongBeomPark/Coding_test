```
class Solution {
    public String solution(String s, int n) {
        String arr[] = s.split("");
        for(int i = 0; i < s.length(); i++){
            if(!(arr[i].equals(" "))){
                int value = arr[i].charAt(0);
                int plus_value = value + n;
                if(value >= 65 && value <= 90) {
                	if(plus_value > 90) {
                		plus_value -= 26;
                	}
                }
                else if(value >= 97 && value <= 122) {
                	if(plus_value > 122) {
                		plus_value -= 26;
                	}
                }
                String str = Character.toString((char)plus_value);
                arr[i] = str;
            }
        }
        String answer = String.join("",arr);
        return answer;
    }
}
```
