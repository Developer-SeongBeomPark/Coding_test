## 접근방법
sort 함수 사용


## 코드
<pre><code>
N = int(input())
dp = [0] * N
for i in range(N):
    dp[i] = int(input())

dp.sort()
for i in dp:
    print(i)
</code></pre>

