```
import java.util.Arrays;

class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = false;
        Arrays.sort(phone_book);
        for(int i = 0; i < phone_book.length-1; i++) {
        	if(phone_book[i+1].length() <= phone_book[i].length()) continue;
        	if(phone_book[i].equals(phone_book[i+1].substring(0,phone_book[i].length()))) return answer;
        }
        answer = true;
        return answer;
    }
}
```

* 숫자로된 문자열로 구성된 배열의 경우 ex) String arr[3] = {"1234","1000","123"};<br>
이를 정렬할 시(Arrays.sort(arr)), 숫자의 크기대로 정렬하는게 아니라 사전 순으로 정렬하게 된다.<br>
즉, 이를 정렬할 경우 {"1000","123","1234"} 가 결과값이다.
 
