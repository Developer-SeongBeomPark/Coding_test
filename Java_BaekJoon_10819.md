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

</code></pre>
