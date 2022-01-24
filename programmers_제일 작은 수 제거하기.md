```
import java.util.*;
import java.io.*;

class Solution {
    public int[] solution(int[] arr) {
        if(arr.length == 1) {
			int[] answer = {-1};
			return answer;
		}
		
		List<Integer> list = new ArrayList<Integer>();
		for(int value : arr) {
			list.add(value);
		}
		int idx = list.indexOf(Collections.min(list));
		list.remove(idx);		
				
				
        int[] answer = new int[list.size()];
        for(int i = 0; i < list.size(); i++) {
        	answer[i] = list.get(i);
        }
        return answer;
    }
}
```
