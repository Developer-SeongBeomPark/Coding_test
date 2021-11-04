## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static int K, V, E;
	static String[] list;
	static int[] graph;
	static int[] color_list;
	static final int Black = 1, White = -1;
	static boolean[] visited;
	static String[] answer_list;
	
	public static void main(String[] args) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		K = Integer.parseInt(br.readLine());
		answer_list = new String[K];
		for(int i = 0; i < K; i++) {
			list = br.readLine().split(" ");
			V = Integer.parseInt(list[0]);
			E = Integer.parseInt(list[1]);
			graph = new int[V+1];
			visited = new boolean[V+1];
			color_list = new int[V+1];
			
			for(int j = 0; j < E; j++) {
				list = br.readLine().split(" ");
				graph[Integer.parseInt(list[0])] = Integer.parseInt(list[1]);
			}
			
			
		}
		}
		
		
	static void dfs(int node) {
		for(int i = 1; i < V; i++) {
			if(visited[i]) continue;
			else {
				visited[i] = true;
				dfs(graph[i]);
				
			}
		}
		
	}
		
	static void bfs() {
		
	}
	
	
	
	
}
</code></pre>
