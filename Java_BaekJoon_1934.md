## 코드 1
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int T;
	static String[] list;
	static int[][] input_value_list;
	static int A,B;
	static int GCD;
	static int LCM;
	public static void main(String args[]) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		T = Integer.parseInt(br.readLine());
		input_value_list = new int[T][2];
		for(int i = 0; i < T; i++) {
			list = br.readLine().split(" ");
			input_value_list[i][0] = Integer.parseInt(list[0]);
			input_value_list[i][1] = Integer.parseInt(list[1]);
		}
		
		for(int i = 0; i < T; i++) {
			A = input_value_list[i][0];
			B = input_value_list[i][1];
			if(A == B) {
				System.out.println(A);
				continue;
			}
			if(A < B) {
				for(int j = 1; j <= A; j++) {
					if(A % j == 0 && B % j == 0) GCD = j;
				}
			}				
			else{
				for(int j = 1; j <= B; j++) {
					if(A % j == 0 && B % j == 0) GCD = j;
				}
			}
			LCM = A * B / GCD;
			System.out.println(LCM);
		}	
	}
}
</code></pre>

## 코드 2
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int T;
	static String[] list;
	static int[][] input_value_list;
	static int A,B;
	static int GCD;
	static int LCM;
	public static void main(String args[]) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		T = Integer.parseInt(br.readLine());
		input_value_list = new int[T][2];
		for(int i = 0; i < T; i++) {
			list = br.readLine().split(" ");
			input_value_list[i][0] = Integer.parseInt(list[0]);
			input_value_list[i][1] = Integer.parseInt(list[1]);
		}
		
		for(int i = 0; i < T; i++) {
			A = input_value_list[i][0];
			B = input_value_list[i][1];
			if(A > B) {
				GCD = GCD_function(A,B);
			}
			else {
				GCD = GCD_function(B,A);
			}
			LCM = A * B / GCD;
			System.out.println(LCM);
		}	
	}
	
	public static int GCD_function(int x, int y) {
		while(y != 0) {
			int r = x % y;
			x = y;
			y = r;
		}
		return x;
	}
}
</code></pre>
