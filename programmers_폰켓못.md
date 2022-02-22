```
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int count = 0;
        
        Arrays.sort(nums);
        int value = 0;
        for(int i : nums) {
        	if(value != i) {
        		count++;
        		value = i;
        	}
        	if(count > (nums.length / 2) - 1) break;
        }
        
        
        return count;
    }
}
```
