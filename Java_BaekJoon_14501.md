## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int N;
	static int[][] consulting;
	static String[] str;
	static int[] dp;
	
	public static void main(String[] args) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		consulting = new int[N+1][2];
		for(int i = 1; i < N+1; i++) {
			str = br.readLine().split(" ");
			consulting[i][0] = Integer.parseInt(str[0]);
			consulting[i][1] = Integer.parseInt(str[1]);
		}
		
		dp = new int[N+1];
		int dp_value = 0, date, max = 0;
		
		for(int i = 1; i < N+1; i++) {
				date = i;
				while(date + consulting[date][0] <= N+1) {
					dp_value += consulting[date][1];
					date += consulting[date][0];
					if(date == N+1) {
						break;
					}
				}
				dp[i] = dp_value;
				max = Math.max(max, dp_value);
				dp_value = 0;
			}
		System.out.println(max);
	}
} 
</code></pre>
