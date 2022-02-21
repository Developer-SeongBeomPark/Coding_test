```
import java.util.*;

class Solution {
    public int solution(String s) {
        int answer = 0, i = 0;
        List<String> list = new ArrayList<>();
        
        while(i < s.length()) {
        	if(s.charAt(i) < 58) {
        		list.add(s.substring(i, i+1));
        		i++;
        	}
        	else if(s.charAt(i) == 'z') {
        		list.add("0");
        		i += 4;
        	}
        	else if(s.charAt(i) == 'o') {
        		list.add("1");
        		i += 3;
        	}
        	else if(s.charAt(i) == 't') {
        		if(s.charAt(i+1) == 'w') {
        			list.add("2");
        			i += 3;
        		}
        		else if(s.charAt(i+1) == 'h') {
        			list.add("3");
        			i += 5;
        		}
        	}
        	else if(s.charAt(i) == 'f') {
        		if(s.charAt(i+1) == 'o') {
        			list.add("4");
        			i += 4;
        		}
        		else if(s.charAt(i+1) == 'i') {
        			list.add("5");
        			i += 4;
        		}
        	}
        	else if(s.charAt(i) == 's') {
        		if(s.charAt(i+1) == 'i') {
        			list.add("6");
        			i += 3;
        		}
        		else if(s.charAt(i+1) == 'e') {
        			list.add("7");
        			i += 5;
        		}
        	}
        	else if(s.charAt(i) == 'e') {
        		list.add("8");
        		i += 5;
        	}
        	else if(s.charAt(i) == 'n') {
        		list .add("9");
        		i += 4;
        	}
        }
        String[] answer_list = new String[list.size()];
        for(int j = 0; j < list.size(); j++) {
        	answer_list[j] = list.get(j);
        }
        answer = Integer.parseInt(String.join("", answer_list));
        
        
        return answer;
    }
}
```


```
import java.util.*;

class Solution {
    public int solution(String s) {
        int answer = 0;
        StringBuilder sb = new StringBuilder("");
        int len = s.length();
        String[] digits = {"0","1","2","3","4","5","6","7","8","9"};
        String[] alphabets = {"zero","one","two","three","four","five","six","seven","eight","nine"};

        for(int i=0; i<10; i++){
            s = s.replaceAll(alphabets[i],digits[i]);
        }

        return Integer.parseInt(s);
    }
}
```
