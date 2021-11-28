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
		consulting = new int[N][2];
		for(int i = 0; i < N; i++) {
			str = br.readLine().split(" ");
			consulting[i][0] = Integer.parseInt(str[0]);
			consulting[i][1] = Integer.parseInt(str[1]);
		}
		
		dp = new int[N+1];
		
		
		for(int i = 0; i < N; i++) {
				if(i + consulting[i][0] <= N) {
					dp[i + consulting[i][0]] = Math.max(dp[i + consulting[i][0]], dp[i] + consulting[i][1]);
				}
				dp[i+1] = Math.max(dp[i+1], dp[i]);
			}
		System.out.println(dp[N]);
	} 
} 
</code></pre> 
