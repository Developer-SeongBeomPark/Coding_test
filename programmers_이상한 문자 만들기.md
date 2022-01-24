```
class Solution {
    public String solution(String s) {
        String arr[] = s.split("");
        int voca_idx = 0;
        for(int i = 0; i < s.length(); i++){
            if(arr[i].equals(" ")) voca_idx = 0;
            else{
                if(voca_idx % 2 == 0){
                    arr[i] = arr[i].toUpperCase();
                }
                else{
                    arr[i] = arr[i].toLowerCase();
                }
                voca_idx++;
            }
        }
        String answer = String.join("",arr);
        return answer;
    }
}
```
