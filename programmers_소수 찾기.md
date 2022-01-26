```
import java.util.*;

class Solution {
    public int solution(int n) {
        List<Integer> list = new ArrayList<>();
        list.add(2);
        
        if(n == 2) return 1;
        
        for(int i = 3; i <= n; i += 2) {
        	boolean is_divisor = true;
        	for(int value : list) {
                if(value > Math.sqrt(i)) break;
        		if(i % value == 0) {
        			is_divisor = false;
        			break;
        		}
        	}
        	if(is_divisor == true) {
        		list.add(i);
        	}
        }
    	return list.size();
    }
}
```

소수의 특성을 알지 못하면 효율성 검사에서 시간초과로 통과하지 못할 것이다.<br>
※ 소수의 특성:<br>
1. 모든 자연수는 소수의 곱으로 이루어져 있다. 따라서 n이 소수인지 판별하려면, n보다 작은 소수들로 나누어떨어지지 않으면 n도 소수이다.<br>
ex) n = 11, n보다 작은 소수 = {2,3,5,7}, n은 2,3,5,7로 나누어 떨어지지 않기 때문에 n도 소수.<br><br>

2. n이 소수인지 판별할 때, √n 보다 작은 소수에 대해서만 나누어떨어지는지 확인하면 된다.
