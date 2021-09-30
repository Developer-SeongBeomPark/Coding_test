## 접근방식
1. p_list를 오름차순으로 정렬한다.
2. 걸리는 시간을 순차적으로 계속 더해나간다.


## 코드
<pre><code>
N = int(input())
p_list = list(map(int,input().split()))
p_list.sort()
time,total_time = 0,0

for i in range(N):
    time += p_list[i]
    total_time += time

print(total_time)
</code></pre>

