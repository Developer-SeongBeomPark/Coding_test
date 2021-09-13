## 접근 방식
최적 부분 구조(Optimal Substructure) 문제라고 생각했다.
정수가 2일 때부터 최소값을 비교하며 코딩했다.


## 코드
<pre><code>
x = int(input())

dp = [0] * 1000001

for i in range(2,x+1):
    dp[i] = dp[i-1] + 1

    if (i % 2 == 0) :
        dp[i] = min(dp[i], dp[i//2] + 1)
    if (i % 3 == 0) :
        dp[i] = min(dp[i], dp[i//3] + 1)

print(dp[x])
</code></pre>
