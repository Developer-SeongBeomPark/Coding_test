## 알아둬야할 사항
ValueOf 메소드로 형변환 가능.

## 코드
<pre><code>
package practice;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.*;

public class Main {
	public static void main(String[] args) throws IOException{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		String[] current_t = br.readLine().split(":");
		String[] start_t = br.readLine().split(":");
		int[] Current_t = new int[3];
		int[] Start_t = new int[3];
		int[] Answer_t = new int[3];
		String[] Answer = new String[3];
		for(int i = 0; i < 3; i++) {
			Current_t[i] = Integer.parseInt(current_t[i]);
			Start_t[i] = Integer.parseInt(start_t[i]);
		}
		int Current_t_total_second = Current_t[0]*3600 + Current_t[1]*60 + Current_t[2];
		int Start_t_total_second = Start_t[0]*3600 + Start_t[1]*60 + Start_t[2];
		
		
		if(Current_t_total_second < Start_t_total_second) {
			int sub = Start_t_total_second - Current_t_total_second;
			Answer_t[0] = sub / 3600;
			if(Answer_t[0] < 10) {
				String A = "0" + Answer_t[0];
				Answer[0] = A;
			}else {Answer[0] = String.valueOf(Answer_t[0]);}
			sub = sub % 3600;
			Answer_t[1] = sub / 60;
			if(Answer_t[1] < 10) {
				String A = "0" + Answer_t[1];
				Answer[1] = A;
			}else {Answer[1] = String.valueOf(Answer_t[1]);}
			sub = sub % 60;
			Answer_t[2] = sub;
			if(Answer_t[2] < 10) {
				String A = "0" + Answer_t[2];
				Answer[2] = A;
			}else {Answer[2] = String.valueOf(Answer_t[2]);}
		}
		else {
			int sub = 24*3600 - (Current_t_total_second - Start_t_total_second);
			Answer_t[0] = sub / 3600;
			if(Answer_t[0] < 10) {
				String A = "0" + Answer_t[0];
				Answer[0] = A;
			}else {Answer[0] = String.valueOf(Answer_t[0]);}
			sub = sub % 3600;
			Answer_t[1] = sub / 60;
			if(Answer_t[1] < 10) {
				String A = "0" + Answer_t[1];
				Answer[1] = A;
			}else {Answer[1] = String.valueOf(Answer_t[1]);}
			sub = sub % 60;
			Answer_t[2] = sub;
			if(Answer_t[2] < 10) {
				String A = "0" + Answer_t[2];
				Answer[2] = A;
			}else {Answer[2] = String.valueOf(Answer_t[2]);}
		}
		System.out.printf("%s:%s:%s",Answer[0],Answer[1],Answer[2]);
	}
}
</code></pre>
