## 접근방식
1. 끝나는 시간을 기준으로 오름차순으로 정렬. 즉, 끝나는 시간이 빠른 회의 순서로 정렬한다.
2. 시작 시간이 앞 회의의 종료시간보다 크거나 같은 경우 회의를 진행한다.

이를 적용해 만든 코드는 다음과 같다.
<pre><code>
N = int(input())
Conference_time_list = [list(map(int,input().split())) for _ in range(N)]  
Conference_time_list.sort(key = lambda x : x[1])
end_time = Conference_time_list[0][1]
num_of_Conferences = 1

for i in range(1,N):
    if(Conference_time_list[i][0] >= end_time):
        num_of_Conferences += 1
        end_time = Conference_time_list[i][1]

print(num_of_Conferences)
</code></pre>
하지만 88%까지만 해결되고 틀리고 말았다.
예외의 케이스가 존재한다는 의미다.

예외의 경우는 다음과 같았다.
정렬 이후에 끝나는 시간이 같은 회의의 경우, 시작 시간이 작은 순서로 정렬해야 예외가 발생하지 않았다.

ex) 3

    1 3
    
    8 8
    
    4 8
    



## 코드
<pre><code>
N = int(input())
Conference_time_list = [list(map(int,input().split())) for _ in range(N)]  
Conference_time_list.sort(key = lambda x : (x[1], x[0]))
end_time = Conference_time_list[0][1]
num_of_Conferences = 1

for i in range(1,N):
    if(Conference_time_list[i][0] >= end_time):
        num_of_Conferences += 1
        end_time = Conference_time_list[i][1]

print(num_of_Conferences)
</code></pre>
