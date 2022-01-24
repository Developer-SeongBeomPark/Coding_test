```
class Solution {
    public int[] solution(long n) {
        String str = String.valueOf(n);
        String[] arr = str.split("");
        
        int[] answer = new int[str.length()];
        for(int i = 0; i < str.length(); i++){
            answer[i] = Integer.parseInt(arr[str.length() - 1 - i]);
        }
        return answer;
    }
}
```
