## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int N,j=0,k=1;
	static Stack<Integer> answer_list, base_stack, output_stack;
	static Stack<String> answer_stack;
	
	public static void main(String[] args) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		answer_list = new Stack<Integer>();
		for(int i = 0; i < N; i++) {
			answer_list.push(Integer.parseInt(br.readLine()));
		}
		base_stack = new Stack<Integer>();
		output_stack = new Stack<Integer>();
		answer_stack = new Stack<String>();
		
		while(true){
			if(!base_stack.contains(answer_list.get(j))) {
				base_stack.push(k);
				answer_stack.push("+");
				k++;
				if(k > N + 1) {
					System.out.println("NO");
					System.exit(0);
				}
			}
			else {
				int pop_value = base_stack.pop();
				output_stack.push(pop_value);
				answer_stack.push("-");
				j++;
			}
			
			if(output_stack.size() == N) break;
		}
		
		
		for(int i = 0; i < answer_stack.size(); i++) {
			System.out.println(answer_stack.get(i));
		 }
	}
}
</code></pre>
