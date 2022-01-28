```
import java.util.*;
class Solution {
    public int[] solution(int[] arr, int divisor) {
        List<Integer> list = new ArrayList<>();
        int count = 0;
        for(int value : arr){
            if(value % divisor == 0){
                list.add(value);
                count++;
            }
        }
        if(count == 0) list.add(-1);
        Collections.sort(list);
        int list_size = list.size();
        int[] answer = new int[list_size];
        for(int i = 0; i < list_size; i++){
            answer[i] = list.get(i);
        }
        return answer;
    }
}
```

* 배열 절렬 :  오름 차순 --> Arrays.sort(arr)  내림 차순 --> Arrays.sort(arr, Collections.reverseOrder())
* 리스트 정렬 : 오름 차순 --> Collections.sort(arr) 내림차순 --> Collections.sort(arr,Collections.reverseOrder())
