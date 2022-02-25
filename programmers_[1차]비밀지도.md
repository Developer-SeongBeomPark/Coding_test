```
class Solution {
    public String[] solution(int n, int[] arr1, int[] arr2) {
        String[] answer_arr1 = new String[n];
        String[] answer_arr2 = new String[n];
        String[] answer = new String[n];
        
        for(int i = 0; i < n; i++) {
        	answer_arr1[i] = Integer.toBinaryString(arr1[i]);
        	while(answer_arr1[i].length() < n) {
        		answer_arr1[i] = " " + answer_arr1[i];
        	}
        	
        	answer_arr2[i] = Integer.toBinaryString(arr2[i]);
        	while(answer_arr2[i].length() < n) {
        		answer_arr2[i] = " " + answer_arr2[i];
        	}
        	
        	answer[i] = "";
        }
        
        for(int i = 0; i < n; i++) {
        	for(int j = 0; j < n; j++) {
        		if(answer_arr1[i].charAt(j) == '1' || answer_arr2[i].charAt(j) == '1') {
        			answer[i] += "#";
        		}
        		else answer[i] += " ";
        	}
        }
        
        
        return answer;
    }
}
```


```
class Solution {
    public String[] solution(int n, int[] arr1, int[] arr2) {
        String[] answer = new String[n];
        
        for(int i = 0; i < n; i++) {
        	answer[i] = Integer.toBinaryString(arr1[i] | arr2[i]);
        	while(answer[i].length() < n) {
        		answer[i] = " " + answer[i];
        	}
        }
        
        for(int i = 0; i < n; i++) {
        	answer[i] = answer[i].replaceAll("1", "#");
        	answer[i] = answer[i].replaceAll("0", " ");
        }
        
        
        return answer;
    }
}
```

* OR 연산자(|)<br>
두 개의 피연산자의 해당 비트 중 어느 한 쪽이 1이면 1을 반환하고, 아니면 0을 반환한다.
