```
class Solution {
    public long solution(long n) {
        long answer = 0;
        double sqrt_value = Math.sqrt(n);
        long int_value = (long) sqrt_value;
        if(sqrt_value - int_value == 0) {
        	answer = (long) Math.pow(int_value+1, 2);
        }
        else {
        	return -1;
        }
        
        return answer;
    }
}
```

```


class Solution {
  public long solution(long n) {
      if (Math.pow((int)Math.sqrt(n), 2) == n) {
            return (long) Math.pow(Math.sqrt(n) + 1, 2);
        }

        return -1;
  }
}
```
