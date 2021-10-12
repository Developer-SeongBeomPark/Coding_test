## 접근방식



## 코드
<pre><code>
N = int(input())
test_case = [list(map(str,input().split())) for _ in range(N)]

for i in range(N):
    for voca in test_case[i]:
        print(voca[::-1],end=" ")
    print()
</code></pre>
