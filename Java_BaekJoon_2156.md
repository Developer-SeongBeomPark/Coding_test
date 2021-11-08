## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int input_value, n, max_value;
	static List<Integer> dp;
	static int[] list;
	
	public static void main(String[] args) throws Exception{
			br = new BufferedReader(new InputStreamReader(System.in));
			n = Integer.parseInt(br.readLine());
			list = new int[n];
			for(int i = 0; i < n; i++) {
				input_value = Integer.parseInt(br.readLine());
				list[i] = input_value;
			}
			
			if(n == 1) {
				System.out.println(list[0]);
				System.exit(0);
			}
			else if(n == 2) {
				System.out.println(list[0] + list[1]);
				System.exit(0);
			}
			
			dp = new ArrayList<Integer>();
			dp.add(0);
			dp.add(list[0]);
			dp.add(list[0] + list[1]);
			for(int i = 3; i < n+1; i++) {
				max_value = Math.max(dp.get(i-3) + list[i-1] + list[i-2], dp.get(i-2) + list[i-1]);
				max_value = Math.max(max_value, dp.get(i-1));
				dp.add(max_value);
			}
			System.out.println(dp.get(n));
		}
}
</code></pre>
