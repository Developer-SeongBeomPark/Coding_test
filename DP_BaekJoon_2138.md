## 접근방법
첫 번째 실패 코드:
<pre><code>
N = int(input())
A = list(map(int,input()))
B = list(map(int,input()))
count = 0
i = 0
cycle = 0

def function(Array,x):   
    if(x == 0):
        Array[x] = 1 - Array[x]
        Array[x+1] = 1 - Array[x+1]
    elif(x == N-1):
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
    else:
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
        Array[x+1] = 1 - Array[x+1]
    return Array

while (A != B):
    if (A[i] != B[i]):
        A = function(A,i)
        count += 1
    i += 1

    if (i > N-1):
        i = 0
        cycle += 1
        if(cycle > 1):
            print(-1)
            exit()
print(count)
</code></pre>
두 번째 실패 코드:
<pre><code>
N = int(input())
A = list(map(int,input()))
B = list(map(int,input()))
count = 0

def function(Array,x):   
    if(x == 0):
        Array[x] = 1 - Array[x]
        Array[x+1] = 1 - Array[x+1]
    elif(x == N-1):
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
    else:
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
        Array[x+1] = 1 - Array[x+1]
    return Array

for i in range(N):
    if(A != B):
        A = function(A,i)
        count += 1
    else:
        print(count)
        exit()
if(A == B):
    print(count)
else:
    print(-1)
</code></pre>
정답 코드에 대한 실패 원인:
1. 첫 번째 스위치를 눌렀을 때와 안눌렀을 때로 나눠서 생각하지 못한 점.
2. 두 가지 경우 중 두 번째 경우에 대한 코드를 작성할 때, 얕은 복사를 이용해야 id 값이 달라서 원래의 변수가 변하지 않는데 
"=" 기호를 사용했더니 깊은 복사가 이루어져 결과값이 달랐었다.


## 코드
<pre><code>
import copy

N = int(input())
A = list(map(int,input()))
A_first_changed = copy.copy(A)
B = list(map(int,input()))
count = 0

def function(Array,x):   
    if(x == 0):
        Array[x] = 1 - Array[x]
        Array[x+1] = 1 - Array[x+1]
    elif(x == N-1):
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
    else:
        Array[x] = 1 - Array[x]
        Array[x-1] = 1 - Array[x-1]
        Array[x+1] = 1 - Array[x+1]
    return Array


for i in range(N-1):
    if(A[i] != B[i]):
        A = function(A,i+1)
        count += 1
    if(A == B):
        print(count)
        exit()

A_first_changed = function(A_first_changed,0)
count = 1

for i in range(N-1):
    if(A_first_changed[i] != B[i]):
        A_first_changed = function(A_first_changed,i+1)
        count += 1
    if(A_first_changed == B):
        print(count)
        exit()

print(-1)
</code></pre>

