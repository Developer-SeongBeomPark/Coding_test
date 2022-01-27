```
import java.util.*;
class Solution {
    public String[] solution(String[] strings, int n) {
    	Arrays.sort(strings,new Comparator<String>() {

			@Override
			public int compare(String o1, String o2) {
				if(o1.charAt(n) == o2.charAt(n)) return o1.compareTo(o2);
				else return o1.charAt(n) - o2.charAt(n);
			}	
    	});
        return strings;
    }
}
```

* 메소드 override 단축키 : Alt + Shift + S,V
* comapreTo 메소드와 compare 메소드에서 return 값이 음수면 전자가 후자보다 작다는 의미이므로 값을 바꾸지 않고, return 값이 양수면 전자가 후자보다 크다는 의미기 때문에 두 개의 값을 바꾼다.
