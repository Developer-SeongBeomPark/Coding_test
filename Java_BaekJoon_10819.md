## 순열 알고리즘
<pre><code>
public class Main{
	static int n = 4;
	static int r = 4;
	static int initArray[] = { 1, 2, 3, 4};
	static int resultArray [] = new int[n];
	static boolean[] visited = new boolean[n];
	
	public static void main(String args[]) throws IOException {
		permutation(0);
	}
	
	static void permutation(int depth) {

		if (depth == r) {
			print();
			return;
		}

		for (int i = 0; i < n; i++) {
			if (!visited[i]) {
				visited[i] = true;
				resultArray[depth] = initArray[i];
				permutation(depth+1);
				visited[i] = false;
			}
		}
	}

	static void print() {
		for (int i = 0; i < r; i++)
			System.out.print(resultArray[i] + " ");

		System.out.println();
	}
}
</code></pre>


## 코드
<pre><code>
import java.util.*;
import java.io.*;

public class Main{
	static int N;
	static int[] arr,temp;
	static String[] list;
	static boolean[] visited;
	static int max_value = 0;
	
	public static void main(String args[]) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		list = br.readLine().split(" ");
		arr = new int[N];
		temp = new int[N];
		visited = new boolean[N];
		for(int i = 0; i < N; i++) {
			arr[i] = Integer.parseInt(list[i]);
		}
		Arrays.sort(arr);
		
		Permutation(0);
		System.out.println(max_value);
	}
	
	static void Permutation(int depth) {
		if(depth == N) {
			int sum = 0;
			for(int i = 0; i < N-1; i++) {
				sum += Math.abs(temp[i] - temp[i+1]);
			}
			max_value = Math.max(max_value, sum);
		}
		
		for(int i = 0; i < N; i++) {
			if(visited[i] == true) continue;
			else {
				visited[i] = true;
				temp[depth] = arr[i];
				Permutation(depth + 1);
				visited[i] = false;
			}
		}
	}
}
</code></pre>
