## 접근방식
M과 N의 범위가 1 ~ 10000이기 때문에 반복문을 사용해도 런타임이 길지 않다.
반복문에서 '루트를 씌운 값' - (int)'루트를 씌운 값' 이 0이 나오면 ArrayList에 추가했다.




## 코드
<pre><code>
import java.io.IOException;
import java.lang.Math;
import java.util.*;

public class Main {

	public static void main(String[] args) throws IOException{
		Scanner input = new Scanner(System.in);
		int M, N, sum = 0;
		List<Integer> dp = new ArrayList<Integer>();
		
		M = input.nextInt();
		input.nextLine();
		N = input.nextInt();
		
		for (int i = M; i <= N; i++) {
			if(Math.sqrt(i) - (int)Math.sqrt(i) == 0) {
				dp.add(i);
			}
		}
		
		if(dp.size() == 0) {
			System.out.println(-1);
		}else {
			for (int i : dp) {
				sum += i;
			}
			System.out.println(sum);
			System.out.println(Collections.min(dp));
		}
		input.close();
	}

}

</code></pre>
