dp로 풀었다

```
class Solution
{
    public int solution(int [][]board)
    {
        int answer = 0;
        int min_value = 0;
        int row_len = board.length;
        int col_len = board[0].length;
        if(row_len == 1 || col_len == 1) return 1;
        int[][] dp = new int[row_len][col_len];
        
        for(int i = 0; i < col_len; i++) {
        	dp[0][i] = board[0][i];
        }
        for(int i = 0; i < row_len; i++) {
        	dp[i][0] = board[i][0];
        }
        
        for(int i = 1; i < row_len; i++) {
        	for(int j = 1; j < col_len; j++) {
        		if(board[i][j] == 1) {
        			if(dp[i-1][j-1] > 0 && dp[i-1][j] > 0 && dp[i][j-1] > 0) {
        				min_value = Math.min(dp[i][j-1],Math.min(dp[i-1][j-1], dp[i-1][j]));
        				dp[i][j] = min_value + 1;
        			}
        			else {
        				dp[i][j] = board[i][j];
        			}
        		}
        		else {
        			dp[i][j] = board[i][j];
        		}
        		answer = Math.max(answer, dp[i][j]);
        	}
        }
        
        return answer * answer;
    }
}
```
