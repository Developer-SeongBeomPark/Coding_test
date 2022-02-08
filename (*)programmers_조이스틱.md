```
class Solution {
    public int solution(String name) {
        int answer = 0;
        int length = name.length();
        int min_move = length - 1;  // 커서를 최소로 움직인 횟수
        for(int i = 0; i < length; i++){
            // i번째 글자에 대해
            char c = name.charAt(i) ;
            // ▲와 ▼ 중 조작 횟수가 적은 것으로 선택
            answer += Math.min(c - 'A', 'Z' - c + 1);

            // 다음 글자부터 A가 연속으로 나올때
            // 어느 방향으로 커서를 이동하는 것이 횟수가 적을지 체크하기 위해
            // A가 연속으로 나오다 끝나는 지점 찾기 (next_index)
            int next_index = i + 1;
            while(next_index < length && name.charAt(next_index) == 'A')
                next_index++;
            
            // 첫글자에서 끝까지 커서를 오른쪽으로만 이동하는 것과
            // i번까지 오른쪽으로 이동하고 왼쪽으로 이동하여 next_index까지 이동하는 것중
            // 조작 횟수가 적은 것을 선택
            // ex) TTAAAAYYY (i=1인 상황, next_index = 6) -> min(8, 2 * 1 + (9 - 6)) = min(8,5) = 5
            min_move = Math.min(min_move, 2 * i + (length - next_index));
        }
        // 최소 커서 이동 횟수 추가
        answer += min_move;
        
        return answer;
    }
}
```
