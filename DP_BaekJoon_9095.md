## 접근방식
 숫자가 1일 때부터 노가다로 갯수를 세어보니
 n > 2일 때,
 f(n) = f(n-1) + f(n-2) + f(n-3)이라는 피보나치 수열과 비슷한 점화식을 파악할 수 있었다.


## 코드
<pre><code>
T = int(input())
n_list = []

dp = [0] * 11

dp[1] = 1
dp[2] = 2
dp[3] = 4

for i in range(4,11):
    dp[i] = dp[i-1] + dp[i-2] + dp[i-3]

for i in range(T):
    n = int(input())
    n_list.append(n)

for i in range(T):
    print(dp[n_list[i]])
</code></pre>
