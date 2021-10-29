## 접근방식
1. DFS를 이용하여 'ㅗ' 모양을 제외한 모든 경우를 구할 수 있다.
2. 'ㅗ'모양은 'ㅗ','ㅓ','ㅏ',ㅜ' 의 경우로 나뉠 수 있고 따로 메소드를 작성한다.


## 코드
<pre><code>
package practice;
import java.io.*;
import java.util.*;

public class Main {
	static BufferedReader br;
	static int N;
	static int M;
	static int[][] arr;
	static boolean[][] visited;
	static int[] dx = {-1,0,1,0};
	static int[] dy = {0,-1,0,1};
	static int max;
	
	public static void DFS(int x, int y, int depth, int sum) {
		if(depth == 4) {
			max = Math.max(max, sum);
			return;
		}
		for(int i  = 0; i < 4; i++) {
			int nx = x + dx[i];
			int ny = y + dy[i];
			if(nx >= 0 && nx < N && ny >= 0 && ny < M && visited[nx][ny] == false) {
				visited[nx][ny] = true;
				DFS(nx,ny,depth+1,sum+arr[nx][ny]);
				visited[nx][ny] = false;
			}
		}
	}
	
	public static void Exception(int x, int y) {
		int wing = 4;    // 가운데에서의 상하좌우 날개
        int min = Integer.MAX_VALUE;
        int sum = arr[x][y];
        for (int i = 0; i < 4; i++) {
            int nx = x + dx[i];
            int ny = y + dy[i];
 
            //날개가 2개이상 없다면 ㅗ 모양이 아니다. 그러므로 함수를 종료한다.
            if (wing <= 2)
                return;
            //날개가 맵 바깥에 있다면 날개가 아니다.
            if (nx < 0 || ny < 0 || nx >= N || ny >= M) {
                wing--;
                continue;
            }
            min = Math.min(min, arr[nx][ny]);
            sum = sum + arr[nx][ny];
        }
        //날개가 4개일때 가장 작은 날개를 없애야 ㅗ,ㅏ,ㅓ,ㅜ 모양이 나온다.
        if (wing == 4) {
            sum = sum - min;
        }
        max = Math.max(max, sum);
	}
	
	
	
	public static void main(String[] args) throws Exception{
		// 입력값에 대한 배열 만들기.
		br = new BufferedReader(new InputStreamReader(System.in));
		String[] str = br.readLine().split(" ");
		N = Integer.valueOf(str[0]);
		M = Integer.valueOf(str[1]);
		
		arr = new int[N][M];
		for(int i = 0; i < N; i++) {
			str = br.readLine().split(" ");
			for(int j = 0; j < M; j++) {
				arr[i][j] = Integer.valueOf(str[j]);
			}
		}
		visited = new boolean[N][M];
		
		// 알고리즘 구현
		
		for(int i = 0; i < N; i++) {
			for(int j = 0; j < M; j++) {
				DFS(i,j,0,0);
				Exception(i,j);
			}
		}
		System.out.println(max);
	}
}
</code></pre>
