## 접근방식
N이 1일 때부터 계속 최대인 경우를 dp에 저장해 놓으면 매번 모든 경우에 해당하는 작업을 다 하지 않아도 기록해놓은 값을 가져다 쓰는
메모이제이션 방식을 사용했다.


## 코드
<pre><code>
import sys

N = int(sys.stdin.readline().strip())

P_list = list(map(int,sys.stdin.readline().split()))
P_list.insert(0,0)

dp = [0] * 10000

for i in range(1,N+1):
    for j in range(1,i+1):
        dp[i] = max(dp[i],P_list[j] + dp[i-j])

print(dp[N])
</code></pre>
