## 코드

<pre><code>
import java.io.*;
import java.util.*;


public class Main{
	static BufferedReader br;
	static int N;
	static String[] arr;
	static int[] int_arr;
	
	public static void main(String[] args) throws Exception {
		br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		arr = new String[N];
		int_arr = new int[N];
		
		arr = br.readLine().split((" "));
		
		for(int i = 0; i < N; i++) {
			int_arr[i] = Integer.parseInt(arr[i]);
		}
		
		if(N == 1) {
			System.out.println((int)Math.pow(int_arr[0], 2));
			return;
		}
		
		
		Arrays.sort(int_arr);
		System.out.println(int_arr[0] * int_arr[N-1]);
		
	}
} 
</code></pre>
