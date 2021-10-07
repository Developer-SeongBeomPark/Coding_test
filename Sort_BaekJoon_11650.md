## 접근방식
1. 입력받은 데이터를 2차원 배열에 넣는다.
2. 0열에 대해서 오름차순으로 정렬하고 1열에 대해 오름차순으로 정렬하기 위해 sort함수의 lambda를 이용한다.


## 코드
<pre><code>
import sys

N = int(sys.stdin.readline())
dp = [list(map(int,sys.stdin.readline().split())) for _ in range(N)]

dp.sort(key = lambda x : (x[0],x[1]))

for i in range(len(dp)):
    print(dp[i][0],dp[i][1])
</code></pre>
