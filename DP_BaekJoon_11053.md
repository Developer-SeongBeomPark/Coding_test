## 접근방식
이 문제는 가장 긴 증가하는 부분 수열이라는 문제인데 풀어봤던 dp 문제 중에선 가장 어려운 것 같다.
어려운 것도 있지만 반복문을 두 번 사용하고 변수를 겹쳐서 사용하기 때문에 헷갈리는 부분이 있었다.
A라는 list의 성분에 대해서 순서대로 확인하면서 dp값(최대 부분 수열 갯수) 의 최대값을 계속 갱신하는 방식으로 코드를 짰다.


## 코드
<pre><code>
import sys

N = int(sys.stdin.readline().strip())
A = list(map(int,sys.stdin.readline().split()))

dp = [1] * 1000

for i in range(N):
    for j in range(i):
        if (A[i] > A[j]):
            dp[i] = max(dp[i], dp[j] + 1)

print(max(dp))
</code></pre>
