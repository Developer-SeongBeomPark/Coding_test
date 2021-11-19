## 코드
<pre><code>
import java.io.*;
import java.util.*;
import java.math.BigInteger;

public class Main{
	static BufferedReader br;
	static String input;
	static List<Integer> answer_stack;
	static BigInteger B_int,n;
	public static void main(String[] args) throws Exception {
		br = new BufferedReader(new InputStreamReader(System.in));
		answer_stack = new ArrayList<Integer>();
		String value = "1";
		while((input = br.readLine()) != null) {
			n = new BigInteger(input);
			while (true){
				B_int = new BigInteger(value);
				if(B_int.subtract(B_int.multiply(B_int.divide(n))) != new BigInteger("0")) {
					value += "1";
				}
				else {
					answer_stack.add(value.length());
					value = "1";
					break;
				}
			}
		}
		
		for(int i = 0; i < answer_stack.size(); i++) {
			System.out.println(answer_stack.get(i));
		}
	}
} 
</code></pre>

--> 메모리 초과.

