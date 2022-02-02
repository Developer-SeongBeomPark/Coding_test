Array를 이용한 답안
```
import java.util.Arrays;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        
        Arrays.sort(participant);
        Arrays.sort(completion);
        
        for(int i = 0; i < completion.length; i++) {
        	if(!(participant[i].equals(completion[i]))) {
        		answer = participant[i];
        		return answer;
        	}
        }
        
        answer = participant[participant.length-1];
        return answer;
    }
}
```

HashMap을 이용한 답안
'''
import java.util.*;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        
        HashMap<String,Integer> hm = new HashMap<>();
        for(String key : participant) {
        	hm.put(key,hm.getOrDefault(key, 0)+1);
        }
        for(String key : completion){
        	hm.put(key,hm.get(key)-1);
        }
        
        for(String key : hm.keySet()) {
        	if(hm.get(key) != 0) {
        		answer = key;
        		break;
        	}
        }
        
        return answer;
    }
}
'''
