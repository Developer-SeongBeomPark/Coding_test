## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static int N;
	static int min_value = Integer.MAX_VALUE;
	static String[] list;
	static int[] int_list;
	static int[] temp;
	static int[][] W;
	static boolean[] visited;
	
	public static void Permutation(int depth) {
		if(depth == N) {
			int sum = 0, value;
			for(int i = 0; i < N; i++) {
				if(i == N-1) {
					value = W[temp[i]-1][temp[0]-1];
				}else {
					value = W[temp[i]-1][temp[i+1]-1];
				}
				if(value == 0) {sum = Integer.MAX_VALUE; break;}
				sum += value;
			}
			min_value = Math.min(sum, min_value);
			
		}
		for(int i = 0; i < N; i++) {
			if(visited[i]) continue;
			else{
				visited[i] = true;
				temp[depth] = int_list[i];
				Permutation(depth + 1);
				visited[i] = false;
			}
		}
	}
	
	public static void main(String args[]) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		W = new int[N][N];
		int_list = new int[N];
		temp = new int[N];
		visited = new boolean[N];
		for(int i = 0; i < N; i++) {
			int_list[i] = i+1;
			list = br.readLine().split(" ");
			for(int j = 0; j < N; j++) {
				W[i][j] = Integer.parseInt(list[j]);
			}
		}
		
		Permutation(0);
		System.out.println(min_value);
	}
}
</code></pre>
