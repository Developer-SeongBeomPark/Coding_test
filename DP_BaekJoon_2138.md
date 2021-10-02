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


## 코드
<pre><code>

</code></pre>

