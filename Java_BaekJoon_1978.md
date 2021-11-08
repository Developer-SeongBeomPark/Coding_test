## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static String[] list;
	static int N, count, total;
	
	public static void main(String[] args) throws Exception{
			br = new BufferedReader(new InputStreamReader(System.in));
			N = Integer.parseInt(br.readLine());
			list = br.readLine().split(" ");
			total = 0;
			
			for(int i = 0; i < list.length; i++) {
				count = 0;
				int check_value = Integer.parseInt(list[i]);
				for(int j = 1; j <= check_value; j++) {
					if(check_value % j == 0) count += 1;
					if(count > 2) break;
				}
				if(count == 2) total += 1;
			}
			System.out.println(total);
		}
}
</code></pre>
