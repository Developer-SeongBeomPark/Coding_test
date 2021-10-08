## 접근방식
N = 20 이고 K = 2일 경우 방정식으로 나타내면 x + y = 20이다.<br>
이는 x = 0, x = 1, x = 2, x = 3......... x = 20 까지의 합이다.<br>
마찬가지로 x + y + z = 20 일 경우, 이는 x + y =0, x + y = 1 ........ x + y = 20 의 합으로 나타낼 수 있다.<br>
이로부터 메모이제이션을 이용하면 되겠다는 생각을 할 수 있고 손코딩으로 다음과 같이 나타내었다.<br>
dp = [[0] * (N+1) for _ in range(K+1)]<br>
dp[1] = [1] * (N+1)<br>
dp[2] = [1, dp[1][0]+dp[1][1], dp[1][0]+dp[1][1]+dp[1][2], .........]<br>
dp[3] = [1, dp[2][0]+dp[2][1], dp[2][0]+dp[2][1]+dp[2][2], .........]<br>

이와 같은 규칙을 가지고 코드를 작성했다.

## 코드
<pre><code>
import sys

N,K = map(int,sys.stdin.readline().split())
dp = [[0] * (N+1) for _ in range(K+1)]
dp[1] = [1] * (N+1)

for i in range(2,K+1):
    for j in range(N+1):
        if(j == 0):
            dp[i][j] = 1
        else:
            for k in range(j+1):
                dp[i][j] += dp[i-1][k]

print(dp[K][N] % 1000000000)
</code></pre>
