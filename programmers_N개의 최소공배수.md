```
import java.util.*;

class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        int gcd = 0;
        Arrays.sort(arr);
        
        if(arr.length == 1) return arr[0];
        if(arr.length == 2) return LCM(arr[0],arr[1],GCD(arr[0],arr[1]));
        
        gcd = GCD(arr[0],arr[1]);
        answer = LCM(arr[0],arr[1],GCD(arr[0],arr[1]));
        
        for(int i = 2; i < arr.length; i++) {
        	gcd = GCD(gcd,arr[i]);
        	answer = LCM(answer,arr[i],GCD(answer,arr[i]));
        }
        
        
        return answer;
    }
    
    public int GCD(int a, int b) {
    	if(b == 0) return a;
    	else return GCD(b,a%b);
    }
    
    public int LCM(int a, int b, int gcd) {
    	return a * b / gcd;
    }
}
```
