## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main {

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int n = Integer.parseInt(br.readLine());
		int[][] list = new int[n][n];
		for(int i = 0; i < n; i++) {
			String[] row = br.readLine().split("");
			for(int j = 0; j < n; j++) {
				list[i][j] = Integer.parseInt(row[j]);
			}
		}
		
		
		
	}
}
</code></pre>
 
