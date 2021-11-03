## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static String[] list;
	static String[][] input;
	static int t, GCD;
	static long sum = 0;
	public static void main(String[] args) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		t = Integer.parseInt(br.readLine());
		input = new String[t][];
		for(int i = 0; i < t; i++) {
			list = br.readLine().split(" ");
			input[i] = list;
		}
		
		for(int i = 0; i < t; i++) {
			for(int j = 1; j < input[i].length - 1; j++) {
				for(int k = j + 1; k < input[i].length; k++) {
					GCD = GCD_Func(Integer.parseInt(input[i][j]), Integer.parseInt(input[i][k]));
					sum += GCD;
				}
			}
			System.out.println(sum);
			sum = 0;
		}
		
		
		
		
		
	}
	
	public static int GCD_Func(int x, int y) {
		if(x > y) {
			while(y != 0) {
				int r = x % y;
				x = y;
				y = r;
			}
			return x;
		}
		else {
			while(x != 0) {
				int r = y % x;
				y = x;
				x = r;
			}
			return y;
		}
	}
}
</code></pre>
