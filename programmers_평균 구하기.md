```
class Solution {
    public double solution(int[] arr) {
        int len = arr.length;
        int sum = 0;
        for(int value : arr){
            sum += value;
        }
        double answer = (double)sum / (double)len;
        return answer;
    }
}
```
