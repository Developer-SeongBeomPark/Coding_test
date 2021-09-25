## 접근방식
1. 제곱수를 모아놓은 pow_list이라는 이름의 리스트를 만든다.
2. dp[2]부터 매 회 최소개수를 저장한다. 점화식은 dp[i] = dp[x] + dp[i-x]라 할 수 있다. 여기서 x는 제곱수를 의미한다.


## 코드
<pre><code>
import sys
from math import pow

N = int(sys.stdin.readline().strip())
dp = [0] * (N+1)
dp[1] = 1
x = 1
pow_list = []

k = 1
while True:
    pow_value = pow(k,2)
    if(pow_value <= N):
        pow_list.append(pow_value)
    else:
        break
    k += 1

for i in range(2,N+1):
    if (i in pow_list):
        x = i
        dp[i] = 1
        continue
    dp[i] = dp[x] + dp[i-x]

print(dp[N])
</code></pre>


## 의문점
내 코드에 전혀 이상한 점이 없다고 생각한다. 하지만 제출을 했더니 메모리 에러도 아니고 그냥 틀렸다고 나온다.<br>
구글에 검색해 정답을 맞춘 사람들의 코드를 참고해봐도 내가 짠 코드에는 이상이 없었다.<br>
VS Code에 내 코드와 맞춘 사람들의 코드를 비교하기 위해 계산 횟수가 많이 필요한 숫자를 넣어봤는데 내가 짠 코드가 더 빨리 계산했다.
