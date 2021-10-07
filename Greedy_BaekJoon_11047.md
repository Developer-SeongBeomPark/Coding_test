## 접근방식
주어진 동전들의 액수에 대해서 액수가 큰 동전을 많이 사용할수록 사용하는 동전의 총 개수를 최소화할 수 있다.<br>
A_list를 내림차순으로 바꿔 사용할 수 있지만 sort함수를 사용하면 시간복잡도가 너무 커지므로 반복문에서 순서만 역순으로 바꿔 처리했다.<br>
두 번째 반복문에서 K값을 줄여나갈 때, "%"를 사용해 처리하는 방법도 있다. 하지만 예외 케이스가 존재하기 때문에 일일이 빼주는 방법을 선택했다. 
예를 들어 K 값이 4201일 경우, K값이 4201, 201, 1, 1, 1, 1 ..... 이렇게 처리된다.



## 코드
<pre><code>
N,K = map(int,input().split())
A_list = []
coin = 0

for i in range(N):
    value = int(input())
    A_list.append(value)

for i in range(len(A_list)-1,-1,-1):
    if(A_list[i] <= K):
        share = K // A_list[i]
        K -= A_list[i] * share
        coin += share
        if(K == 0):
            print(coin)
            break
</code></pre>
