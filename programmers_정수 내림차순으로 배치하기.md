```
import java.util.*;

class Solution {
    public long solution(long n) {
		String str = String.valueOf(n);
		String[] arr = str.split("");
		Arrays.sort(arr,Collections.reverseOrder());
		String value = String.join("", arr);
        long answer = Long.parseLong(value);
        return answer;
    }
}
```
