## 알아둬야할 사항
Comparator에서 다중 조건 처리하는 방법.

## 코드
<pre><code>
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.*;

public class Main {
	static class student_info {
		int day, month, year;
		String name;
		
		public student_info(String name, int day, int month, int year) {
			this.name = name;
			this.day = day;
			this.month = month;
			this.year = year;
		}
	}
		
	public static void main(String[] args) throws IOException{		
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int n = Integer.parseInt(br.readLine());
		ArrayList<student_info> list = new ArrayList<>();
		while(n-- > 0) {
			String[] array = br.readLine().split(" ");
			student_info student = new student_info(array[0], Integer.parseInt(array[1]), Integer.parseInt(array[2]), Integer.parseInt(array[3]));
			list.add(student);
			}
		
		list.sort(new Comparator<student_info>(){
			public int compare(student_info arg0,student_info arg1) {
				if(arg0.year > arg1.year) {
					return 1;
				}
				else if(arg0.year == arg1.year) {
					if(arg0.month > arg1.month) {
						return 1;
					}
					else if(arg0.month == arg1.month) {
						if(arg0.day > arg1.day) {
							return 1;
						}
						else if(arg0.day == arg1.day) {
							return 0;
						}
						else {
							return -1;
						}
					}
					else {
						return -1;
					}
				}
				else {
					return -1;
				}
			}
		});	
		System.out.println(list.get(list.size()-1).name);
		System.out.println(list.get(0).name);
		}
}
</code></pre>
