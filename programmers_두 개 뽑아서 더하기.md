```
import java.util.Arrays;
import java.util.HashSet;

class Solution {
    public Integer[] solution(int[] numbers) {
        
        HashSet<Integer> hs = new HashSet<>();
        for(int i = 0; i < numbers.length-1; i++) {
        	for(int j = i+1; j < numbers.length; j++) {
        		int value = numbers[i] + numbers[j];
        		hs.add(value);
        	}
        }
        Integer[] arr = hs.toArray(new Integer[hs.size()]);
        Arrays.sort(arr);
        return arr;
    }
}
```
