```
class Solution {
    public int solution(int n) {
        int answer = 0;
        int input_value_count = 0;
        String input_binary = Integer.toBinaryString(n);
        for(int i = 0; i < input_binary.length(); i++) {
        	if(input_binary.charAt(i) == '1') input_value_count++;
        }
        
        
        while(true) {
        	n++;
        	String a = Integer.toBinaryString(n);
        	int output_value_count = 0;
        	for(int i = 0; i < a.length(); i++) {
        		if(a.charAt(i) == '1') output_value_count++;
        	}
        	if(output_value_count == input_value_count) {
        		answer = n;
        		break;
        	}
        }
        
        return answer;
    }
}
```


'''
import java.lang.Integer;

class TryHelloWorld
{
    public int nextBigNumber(int n)
    {
      int a = Integer.bitCount(n);
      int compare = n+1;

      while(true) {
        if(Integer.bitCount(compare)==a)
          break;
        compare++;
      }

      return compare;
    }

    public static void main(String[] args)
    {
        TryHelloWorld test = new TryHelloWorld();
        int n = 78;
        System.out.println(test.nextBigNumber(n));
    }
}
'''
