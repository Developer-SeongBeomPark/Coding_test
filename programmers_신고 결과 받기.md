```
class Solution {
    public int[] solution(String[] id_list, String[] report, int k) {
    	int len = id_list.length;
        int[] answer = new int[len];
        int[][] dp = new int[len][len];
        
        String[][] report_arr = new String[report.length][2];

        for(int i = 0; i < report.length; i++) {
        	report_arr[i] = report[i].split(" ");
        	int x = 0, y = 0;
        	for(int j = 0; j < len; j++) {
        		if(report_arr[i][0].equals(id_list[j])) x = j;
        		if(report_arr[i][1].equals(id_list[j])) y = j;
        	}
        	if(dp[x][y] < 1) dp[x][y]++;
        }
        
        for(int i = 0; i < len; i++) {
        	int sum = 0;
        	for(int j = 0; j < len; j++) {
        		if(dp[j][i] > 0) sum++;
        	}
        	if(sum >= k) {
        		for(int s = 0; s < len; s++) {
        			if(dp[s][i] > 0) answer[s] ++;
        		}
        	}
        	
        }
        
        return answer;
    }
}
```
