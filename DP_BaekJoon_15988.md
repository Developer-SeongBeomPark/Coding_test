## 접근방법



### 시간 초과 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main {

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int n = Integer.parseInt(br.readLine());
		int dp[] = new int[1000001];
		dp[0] = 0;
		dp[1] = 1;
		dp[2] = 2;
		dp[3] = 4;
		
		List<Integer> input_list = new ArrayList<Integer>();
		for(int i = 0; i < n; i++) {
			int value = Integer.parseInt(br.readLine());
			input_list.add(value);
		}
		
		for(int i = 4; i <= Collections.max(input_list); i++) {
			dp[i] = dp[i-1] + dp[i-2] + dp[i-3];
		}
		
		for(int i = 0; i < input_list.size(); i++) {
			System.out.println(dp[input_list.get(i)]);
		}
	}
}
</code></pre>

## 코드
<pre><code>

</code></pre>
