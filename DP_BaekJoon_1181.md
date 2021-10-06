## 접근방식
1. 입력되는 문자열을 dp라는 2차원 배열에 저장한다.
2. 문자열의 크기와 같은 숫자의 dp 인덱스에 해당 문자열을 추가한다.
3. 입력값이 모두 입력되면 set 자료형을 이용해 중복되는 문자열을 삭제시키고 다시 리스트로 바꾸어 sort함수를 이용해 오름차순으로 나열한다.



## 코드
<pre><code>
dp = [[] for _ in range(51)]

N = int(input())
for i in range(N):
    string = input()
    dp[len(string)].append(string)

for i in range(1,len(dp)):
    if(len(dp[i]) > 1):
        dp[i] = list(set(dp[i]))
        dp[i].sort()

for i in range(1,len(dp)):
    if(len(dp[i]) > 0):
        for source_value in dp[i]:
            print(source_value)
</code></pre>
