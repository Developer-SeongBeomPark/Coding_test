## 접근방식
1. 각 단계에 대해 최대값을 갱신해나간다
2. 최대값들을 모아놓은 배열에서의 최대값을 출력한다.

## 코드
<pre><code>
n = int(input())
A = list(map(int,input().split()))

temp = [0 for _ in range(n)]

for i in range(n):
    temp[i] = max(temp[i-1] + A[i], A[i])

print(max(temp))
</code></pre>
