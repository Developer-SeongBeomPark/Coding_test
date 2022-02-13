```
class Solution {
    public int solution(int n) {
        int[] arr = new int[n+1];
        arr[0] = 0;
        arr[1] = 1;
        for(int i = 2; i <= n; i++) {
        	arr[i] = arr[i-1] + arr[i-2];
        	arr[i] %= 1234567;
        }
 
        return arr[n];
    }
}
```

피보나치 수는 44번째만 가도 int형의 범위를 넘어버릴 정도로 기하급수적으로 증가하는 수열이므로 n번째 피보나치 수를 구하는 것은 불가능하다.
그렇기 때문에 모듈러 연산의 성질을 이용해야한다.
