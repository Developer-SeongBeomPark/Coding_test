```
import java.util.*;

class Solution {
    public int[] solution(int N, int[] stages) {
        int[] answer = new int[N];
        
        int[][] arr = new int[N][2];
        double[][] answer_arr = new double[N][2];
        
        for(int i = 0; i < stages.length; i++) {
        	if(stages[i] == N+1) {
        		for(int j = 0; j < N; j++) {
        			arr[j][1]++;
        		}
        	}
        	else {
        		arr[stages[i]-1][0]++;
            	for(int j = 0; j < stages[i]; j++) {
            		arr[j][1]++;
            	}
            }
        }
        
        for(int i = 0; i < arr.length; i++) {
        	answer_arr[i][0] = i+1;
        	if(arr[i][1] == 0) {
        		answer_arr[i][1] = 0;
        	}
        	else {
        		answer_arr[i][1] = (double)arr[i][0] / arr[i][1];
        	}
        }
        
        Arrays.sort(answer_arr, new Comparator<double[]>() {

			@Override
			public int compare(double[] o1, double[] o2) {
				if(o1[1] == o2[1]) {
					return Double.compare(o1[0], o2[0]);
				}
				else {
					return Double.compare(o2[1], o1[1]);
				}
			}
        	
        });
        	
			
        for(int i = 0; i < N; i++) {
        	answer[i] = (int)answer_arr[i][0];
        }
        
        return answer;
    }
}
```
