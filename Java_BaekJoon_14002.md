## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int N,max = 0,max_index;
	static String[] list;
	static int[] Integer_list,dp;
	static List<ArrayList<String>> answer_list;
	
	public static void main(String[] args) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		list = br.readLine().split(" ");
		Integer_list = new int[N];
		dp = new int[N];
		answer_list = new ArrayList<ArrayList<String>>();
		
		if(N == 1) {
			System.out.println(1);
			System.out.println(list[0]);
			System.exit(0);
		}
		
		for(int i = 0; i < N; i++) {
			Integer_list[i] = Integer.parseInt(list[i]);
		}
		dp[0] = 1;
		ArrayList<String> row = new ArrayList<String>();
		row.add(String.valueOf(Integer_list[0]));
		answer_list.add(row);
		
		for(int i = 1; i < N; i++) {
			ArrayList<String> r = new ArrayList<String>();
			for(int j = 0; j < i; j++) {
				if(Integer_list[i] > Integer_list[j]) {
					if(dp[i] < dp[j] + 1) {
						dp[i] = dp[j] + 1;
						max = Math.max(max, dp[i]);
						max_index = i;
						
						ArrayList<String> temp = answer_list.get(j);
						temp.add(String.valueOf(Integer_list[i]));
					}
				}
			}
			if(r.isEmpty()) {
				dp[i] = 1;
				r.add(String.valueOf(Integer_list[i]));
			}
			answer_list.add(r);
		}
		System.out.println(max);
		for(int i = 0; i < answer_list.size(); i++) {
			String str = String.join(" ", answer_list.get(i));
			System.out.println(str);
		}
		
		
	}
} 
</code></pre>
