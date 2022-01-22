```
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;

public class practice {
	static BufferedReader br;
	static BufferedWriter bw;
	static String str[];
	static int n,m;
	
	public static void main(String[] args) throws IOException{
		br = new BufferedReader(new InputStreamReader(System.in));
		bw = new BufferedWriter(new OutputStreamWriter(System.out));
		str = br.readLine().split(" ");
		n = Integer.parseInt(str[0]);
	    m = Integer.parseInt(str[1]);
	        
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++) {
            	bw.write("*");
            }
            bw.write("\n");
        }
	        
	    bw.close();

	}

}
```
