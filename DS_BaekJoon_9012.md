## 접근방식
1. 입력된 데이터를 0번째 인덱스부터 확인해간다.
2. 스택에 각 인덱스에 해당하는 값을 push한다.
3. push된 값이 ')'인 경우에 그 앞의 값이 '('라면 이 둘을 pop시킨다.


※ 주의<br>
input_value를 입력받을때 sys.stdin.readline()을 이용했었는데 에러가 나서 디버깅을 해봤더니 input값 끝에 '\n'이 있었다.<br>
이를 해결하기 위해 sys.stdin.readline().strip()을 사용했다.


## 코드
<pre><code>
import sys

N = int(sys.stdin.readline())
bool_list = []

for _ in range(N):
    input_value = str(sys.stdin.readline().strip())
    dp = []
    for i in range(len(input_value)):
        dp.append(input_value[i])
        if (len(dp) > 1):
            if (dp[-1] == ')' and dp[-2] == '('):
                dp.pop()
                dp.pop()
            
    if (len(dp) == 0):
        bool_list.append("YES")
    else:
        bool_list.append("NO")

for bool_value in bool_list:
    print(bool_value)
</code></pre>
