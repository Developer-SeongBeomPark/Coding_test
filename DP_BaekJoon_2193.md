## 접근방식
N이 1일 때부터 primary number의 개수를 세어봤더니 피보나치 수열 꼴의 알고리즘인 것을 알 수 있었다.


## 코드
<pre><code>
N = int(input())
dp = [0] * 91

dp[1] = 1
dp[2] = 1

for i in range(3,N+1):
    dp[i] = dp[i-1] + dp[i-2]

print(dp[N])
</code></pre>
