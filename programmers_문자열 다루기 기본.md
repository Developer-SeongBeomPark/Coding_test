```
class Solution {
    public boolean solution(String s) {
        if(s.length() != 4 && s.length() != 6) return false;
        char[] arr = s.toCharArray();
        int ascii = 0;
        for(char value : arr) {
        	ascii = value;
        	if(ascii > 60) return false;
        }
        
        return true;
    }
}
```
