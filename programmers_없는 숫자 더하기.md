```
class Solution {
    public int solution(int[] numbers) {
        int answer = 0;
        
        int[] arr = {0,1,2,3,4,5,6,7,8,9};
        for(int value : arr){
            boolean int_in = false;
            for(int num_value : numbers){
                if(value == num_value) {
                    int_in = true;
                    break;
            }
            }
                if(int_in == false) answer += value;
            }
        
        return answer;
    }
}
```
