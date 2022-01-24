```
import java.util.*;

public class Solution {
    public int solution(int n) {
        String str = String.valueOf(n);
        String[] arr = str.split("");
        int answer = 0;
        for(int i = 0; i < str.length(); i++){
            answer += Integer.parseInt(arr[i]);
        }
        return answer;
    }
}
```

```
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;

        while(n != 0){
            answer += n % 10;
            n /= 10;
        }

        return answer;
    }
}
```
