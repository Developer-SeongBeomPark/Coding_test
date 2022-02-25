```
class Solution {
    public int solution(int[][] sizes) {
        int max = 0, min = 0;
        
        for(int i = 0; i < sizes.length; i++) {
        	int bigger = Math.max(sizes[i][0], sizes[i][1]);
        	int smaller = Math.min(sizes[i][0], sizes[i][1]);
        	if(bigger > max) max = bigger;
        	if(smaller > min) min = smaller;
        }
        
        return max * min;
    }
}
```
