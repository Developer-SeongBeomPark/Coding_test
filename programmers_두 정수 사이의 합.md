```
class Solution {
    public long solution(int a, int b) {
        long answer = 0;
        int max = Math.max(a,b);
        int min = Math.min(a,b);
        for (int value = min; value <= max; value++){
            answer += value;
        }
        
        return answer;
    }
}
```

```
class Solution {

    public long solution(int a, int b) {
        return sumAtoB(Math.min(a, b), Math.max(b, a));
    }

    private long sumAtoB(long a, long b) {
        return (b - a + 1) * (a + b) / 2;
    }
}
```
