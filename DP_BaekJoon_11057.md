## 접근방식
N이 1일 때부터 4일 때까지의 경우를 모두 나열해보며 규칙을 찾으려고 했다.<br>
dp[i] 리스트의 값들이 이전의 원소의 값들에 영향을 받는다는 것을 알아냈고 이를 코드화했다.<br>
또한, 원하는 값이 dp[i] 값들이 합이므로 이에 해당하는 리스트도 생성하여 i값이 증가함에따라 데이터를 저장하도록 했다.


## 코드
<pre><code>
N = int(input())
dp = [[0]*10 for _ in range(N+1)]
sum_dp = [0] * (N+1)

dp[1] = [1,1,1,1,1,1,1,1,1,1]
sum_dp[1] = 10

if (N < 2):
    print(sum_dp[N] % 10007)
    exit()

for i in range(2,N+1):
    dp[i][0] = sum_dp[i-1]
    for j in range(1,10):
        dp[i][j] = dp[i][j-1] - dp[i-1][j-1]
    sum_dp[i] = sum(dp[i])

print(sum_dp[N] % 10007)
</code></pre>
