## 알아둬야할 사항
BufferReader, InputStreamReader, Comparator, StringBuilder

## 코드
<pre><code>
package practice;
import java.io.IOException;
import java.util.ArrayList;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Comparator;



public class Main {
	static class player{
		int cost;
		String name;
		
		public player(int cost, String name) {
			this.cost = cost;
			this.name = name;
		}	
	}
	public static void main(String[] args) throws IOException{		
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int n = Integer.parseInt(br.readLine());
		StringBuilder string = new StringBuilder();
		
		while(n-- > 0) {
			int p = Integer.parseInt(br.readLine());
			ArrayList<player> list = new ArrayList<>();
			
			while(p-- > 0) {
				String[] array = br.readLine().split(" ");
				list.add(new player(Integer.parseInt(array[0]),array[1]));
				
				list.sort(new Comparator<player>() {
					@Override
					public int compare(player arg0, player arg1) {
						if(arg0.cost < arg1.cost) {
							return 1;
						}else if(arg0.cost == arg1.cost) {
							return 0;
						}else {
							return -1;
						}
					}
				});
			}
			string.append(list.get(0).name + "\n");
		}
		System.out.println(string);
		
	}

}

</code></pre>
