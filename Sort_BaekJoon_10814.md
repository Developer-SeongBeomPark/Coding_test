## 접근 방법
1. 나이에 대해 오름차순으로 정렬하기 위해 sorted함수를 사용했다.
2. 나이가 같은 경우 먼저 등록한 순서로 출력해야하기 때문에 정렬하기 전에 입력 순서대로 0부터 N-1까지 순차적으로 값을 추가한다.
3. lambda식을 이용하여 다중조건으로 정렬한다.

※ 내가 놓친부분
1. 숫자를 자료형으로 받았을 때 숫자처럼 처리가 안된다는 것
2. sorted함수는 a = sorted(a)처럼 초기화가 필요하다. sort함수처럼 a.sort()만 했을때 값이 변하지 않는다.



## 코드
<pre><code>
import sys

N = int(sys.stdin.readline())
database = [list(map(str,sys.stdin.readline().split())) for _ in range(N)]
for i in range(N):
    database[i][0] = int(database[i][0])
    database[i].append(i)
database = sorted(database, key = lambda x : (x[0],x[2]))

for i in range(N):
    print(database[i][0],database[i][1])
</code></pre>
