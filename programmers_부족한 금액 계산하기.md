```
class Solution {
    public long solution(int price, int money, int count) {
        long answer = 0;

        long total = (long)price * count * (count + 1) / 2;
        if(money >= total) return answer;
        else answer = total - money;
        
        return answer;
    }
}
```
