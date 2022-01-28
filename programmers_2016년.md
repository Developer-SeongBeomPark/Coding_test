```
class Solution {
    public String solution(int a, int b) {
        String[] day = {"THU","FRI","SAT","SUN","MON","TUE","WED"};
        int[] month = {0,31,29,31,30,31,30,31,31,30,31,30,31};
        int day_count = 0;
        
        for(int i = 0; i < a; i++){
            day_count += month[i];
        }
        day_count += b;
        
        int day_idx = day_count % 7;
        
        String answer = day[day_idx];
        return answer;
    }
}
```
