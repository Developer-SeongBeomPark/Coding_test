```
class Solution {
	int[][] a;
    public int[][] solution(int[][] arr1, int[][] arr2) {
    	if(arr1[0].length == arr2.length) {
    		int row = arr1.length, col = arr2[0].length;
            int[][] answer = new int[row][col];
            
            for(int i = 0; i < row; i++) {
            	for(int j = 0; j < col; j++) {
            		for(int k = 0; k < arr1[0].length; k++) {
            			answer[i][j] += arr1[i][k] * arr2[k][j];
            		}
            	}
            }
            a = answer;
    	}
    	
    	else {
    		int row = arr2.length, col = arr1[0].length;
            int[][] answer = new int[row][col];
            
            for(int i = 0; i < row; i++) {
            	for(int j = 0; j < col; j++) {
            		for(int k = 0; k < col; k++) {
            			answer[i][j] += arr2[i][k] * arr1[k][j];
            		}
            	}
            }
            a = answer;
    	}
    	
        
        return a;
    }
}
```
