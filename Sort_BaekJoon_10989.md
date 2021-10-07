## 접근방식
1. 최대 숫자가 10000이므로 크기가 10001인 배열을 생성한다.
2. 입력되는 숫자와 동일한 인덱스의 value를 1씩 증가시킨다.
3. value가 1 이상인 인덱스에 대하여 value값 만큼 인덱스를 출력한다.



## 코드
<pre><code>
import sys

N = int(input())
dp = [0] * 10001
for i in range(N):
    input_value = int(sys.stdin.readline())
    dp[input_value] += 1

for i in range(10001):
    if (dp[i] != 0):
        for j in range(dp[i]):
            print(i)
</code></pre>
