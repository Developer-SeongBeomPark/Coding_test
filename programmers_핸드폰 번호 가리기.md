```
class Solution {
    public String solution(String phone_number) {
        int len = phone_number.length();
        String answer = "";
        
        if(len == 4) answer = phone_number;
        else{
            String s = phone_number.substring(len-4);
            String encode = "";
            for(int i = 0; i < len-4; i++){
                encode += "*";
            }
            answer = encode + s;
        }
        return answer;
    }
}
```
