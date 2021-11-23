## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;


public class Main{
	static BufferedReader br;
	static int N, max = 0, value;
	static String[][] matrix, temp_matrix;
	static String[] str;
	
	public static void main(String[] args) throws Exception {
		br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		matrix = new String[N][N];
		temp_matrix = new String[N][N];
		
		// 입력된 행렬을 N X N 행렬에 대입
		for(int i = 0; i < N; i++) {
			str = br.readLine().split("");
			for(int j = 0; j < str.length; j++) {
				matrix[i][j] = str[j];
			}
		}
		
		// 주어진 행위를 동작
		Loop1 :
		for(int i = 0; i < N; i++) {
			Loop2 :
			for(int j = 0; j < N; j++) {
				if(i == N-1 && j == N-1) {
					break Loop1;
				}
				else if(i >= 0 && i < N-1) {
					if(j >= 0 && j < N-1) {
						temp_matrix = column_swap(i,j,matrix);
						value = column_swap_search(i,j,temp_matrix);
						max = Math.max(max, value);
						
						
						temp_matrix = row_swap(i,j,matrix);
						value = row_swap_search(i,j,temp_matrix);
						max = Math.max(max, value);
					}
				}
				else if(i == N-1) {
					temp_matrix = column_swap(i,j,matrix);
					value = column_swap_search(i,j,temp_matrix);
					max = Math.max(max, value);
				}
				else if(j == N-1) {
					temp_matrix = row_swap(i,j,matrix);
					value = row_swap_search(i,j,temp_matrix);
					max = Math.max(max, value);
				}		
			}
		}
		
		System.out.println(max);
		
		
		
		
	}
	
	public static String[][] column_swap(int x, int y, String[][] m) {
		String temp = m[x][y];
		m[x][y] = m[x][y+1];
		m[x][y+1] = temp;
		
		return m;
	}
	
	public static String[][] row_swap(int x, int y, String[][] m) {
		String temp = m[x][y];
		m[x][y] = m[x+1][y];
		m[x+1][y] = temp;
		
		return m;
	}
	
	public static int column_swap_search(int x, int y, String[][] t_matrix) {
		int col_value = 1, max_value = 1, row_value = 1;
		for(int k = 0; k < N-1; k++) {
			if(t_matrix[x][k].equals(t_matrix[x][k+1])) {
				col_value += 1;
			}
			else {
				col_value = 1;
			}
			max_value = Math.max(max_value,col_value);
			
			if(k == y) {
				row_value = 1;
				for(int w = 0; w < N-1; w++) {
					if(t_matrix[w][y].equals(t_matrix[w+1][y])) {
						row_value += 1;
					}
					else {
						row_value = 1;
					}
					max_value = Math.max(max_value,row_value);
					
				}
			}
			else if(k == y+1) {
				row_value = 1;
				for(int w = 0; w < N-1; w++) {
					if(t_matrix[w][y+1].equals(t_matrix[w+1][y+1])) {
						row_value += 1;
					}
					else {
						row_value = 1;
					}
					max_value = Math.max(max_value,row_value);
					
				}
			}
			
		}
		
		return max_value;
	}
	
	public static int row_swap_search(int x, int y, String[][]t_matrix) {
		int row_value = 1, max_value = 1, col_value =1;
		for(int k = 0; k < N-1; k++) {
			if(t_matrix[k][y].equals(t_matrix[k+1][y])) {
				row_value += 1;
			}
			else {
				row_value = 1;
			}
			max_value = Math.max(max_value,row_value);
			
			if(k == x) {
				col_value = 1;
				for(int w = 0; w < N-1; w++) {
					if(t_matrix[x][w].equals(t_matrix[x][w+1])) {
						col_value += 1;
					}
					else {
						col_value = 1;
					}
					max_value = Math.max(max_value,col_value);
					
				}
			}
			else if(k == x+1) {
				col_value = 1;
				for(int w = 0; w < N-1; w++) {
					if(t_matrix[x+1][w].equals(t_matrix[x+1][w+1])) {
						col_value += 1;
					}
					else {
						col_value = 1;
					}
					max_value = Math.max(max_value,col_value);
					
				}
			}
		}
		
		return max_value;
	}
} 
</code></pre>
 
