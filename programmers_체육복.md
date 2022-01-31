```
class Solution {
    public int solution(int n, int[] lost, int[] reserve) {
    	int count = 0;
    	
    	
    	int[] reserve_arr = new int[n+1];
    	int[] lost_arr = new int[n+1];
    	int[] output_arr = new int[n+1];
    	
    	
    	for(int value : lost) {
    		lost_arr[value]--;
    	}
    	for(int value : reserve) {
    		reserve_arr[value]++;
    	}
    	for(int i = 1; i <= n; i++) {
    		output_arr[i] = reserve_arr[i] +  lost_arr[i];
    		
    	}
    	
    	
    	for(int i = 1; i < n+1; i++) {
    		if(output_arr[i] == -1) {
	    		if(i == 1) {
	    			if(output_arr[i+1] == 1) {
	    				output_arr[i]++;
	    				output_arr[i+1]--;
	    			}
	    		}
	    		else if(i == n) {
	    			if(output_arr[i-1] == 1) {
	    				output_arr[i]++;
	    				output_arr[i-1]--;
	    			}
	    		}
	    		else {
	    			if(output_arr[i-1] == 1) {
	    				output_arr[i]++;
	    				output_arr[i-1]--;
	    			}
	    			else {
	    				if(output_arr[i+1] == 1) {
	    					output_arr[i]++;
	    					output_arr[i+1]--;
	    				}
	    			}
	    			
	    		}
    		}
    	}
    	
    	for(int i = 1; i < n+1; i++) {
    		if(output_arr[i] > -1) {
    			count++;
    		}
    	}
    	
        return count;
    }
}
```
