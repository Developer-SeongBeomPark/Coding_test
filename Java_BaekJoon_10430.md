## 코드
<pre><code>
import java.io.*;
import java.util.*;

public class Main{
	static BufferedReader br;
	static String[] list;
	static int A,B,C;
	static int value1,value2,value3,value4;
	public static void main(String args[]) throws Exception{
		br = new BufferedReader(new InputStreamReader(System.in));
		list = br.readLine().split(" ");
		A = Integer.parseInt(list[0]);
		B = Integer.parseInt(list[1]);
		C = Integer.parseInt(list[2]);
		
		value1 = (A+B)%C;
		System.out.println(value1);
		value2 = ((A%C)+(B%C))%C;
		System.out.println(value2);
		value3 = (A*B)%C;
		System.out.println(value3);
		value4 = ((A%C)*(B%C))%C;
		System.out.println(value4);
	}
}
</code></pre>
