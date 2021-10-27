## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main {

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		String[] input = br.readLine().split(" ");
		int[] input_value = new int[3];
		for(int i = 0; i < input.length; i++) {
			input_value[i] = Integer.valueOf(input[i]);
		}
		
		int E = 1;
		int S = 1;
		int M = 1;
		int count = 1;
		
		while(E != input_value[0] || S != input_value[1] || M != input_value[2]) {
			E++;
			S++;
			M++;
			if(E > 15) E = 1;
			if(S > 28) S = 1;
			if(M > 19) M = 1;
			count++;
		}
		
		System.out.println(count);
	}
}
</code></pre>
