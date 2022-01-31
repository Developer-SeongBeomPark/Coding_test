```
class Solution {
    public int solution(int n, int[] lost, int[] reserve) {
    	int count_right = 0;
    	int count_left = 0;
    	
    	int[] reserve_arr = new int[n+1];
    	int[] lost_arr = new int[n+1];
    	int[] output_arr_right = new int[n+1];
    	int[] output_arr_left = new int[n+1];
    	
    	for(int value : lost) {
    		lost_arr[value]--;
    	}
    	for(int value : reserve) {
    		reserve_arr[value]++;
    	}
    	for(int i = 1; i <= n; i++) {
    		output_arr_right[i] = reserve_arr[i] +  lost_arr[i];
    		output_arr_left[i] = reserve_arr[i] +  lost_arr[i];
    	}
    	
    	
    	for(int i = 2; i < n+1; i++) {
    		if(output_arr_right[i] == -1) {
    			if(output_arr_right[i-1] == 1) {
    				output_arr_right[i-1]--;
    				output_arr_right[i]++;
    			}
    		}
    	}
    	
    	for(int i = 1; i < n; i++) {
    		if(output_arr_left[i] == -1) {
    			if(output_arr_left[i+1] == 1) {
    				output_arr_left[i+1]--;
    				output_arr_left[i]++;
    			}
    		}
    	}
    	
    	for(int i = 1; i < n+1; i++) {
    		if(output_arr_right[i] >= 0) {
    			count_right++;
    		}
    		if(output_arr_left[i] >= 0) {
    			count_left++;
    		}
    	}
    	
        return Math.max(count_right, count_left);
    }
}
```
테스트 케이스 7,10번 
