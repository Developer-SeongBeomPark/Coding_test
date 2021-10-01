## 접근방법
1. A 행렬의 (0,0) 인덱스부터 순서대로 조회
2. 해당 인덱스에 대하여 값이 B와 같을 경우 pass, B와 다를 경우 function 함수를 적용한다.
3-1. 매 시행에서 A와 B가 같은지 확인하고 같다면 횟수를 출력하고 프로그램 종료
4. 이중 반복문이 종료되고 나면 A와 B가 다르다는 의미이므로 -1을 출력.


## 코드
<pre><code>
# 3X3 행렬의 원소를 뒤집는 함수
def function(Array_list,x,y):
    for k in range(3):
        for w in range(3):
            if (Array_list[x+k][y+w] == 1):
                Array_list[x+k][y+w] = 0
            else:
                Array_list[x+k][y+w] = 1
    return Array_list

# input값을 저장하고 변수를 초기화
N, M = map(int,input().split())
A = [list(map(int,input())) for _ in range(N)]
B = [list(map(int,input())) for _ in range(N)]
count = 0

# function 함수를 적용할 수 없는 경우
if(N < 3 or M < 3):
    if (A == B): # 3X3 행렬보다 작은 행렬이지만 A행렬과 B 행렬이 같은 경우
        print(0)
        exit()
    print(-1)
    exit()

# 3X3 행렬보다 크기가 크거나 같은 경우
for i in range(N-2):
    for j in range(M-2):
        if (A[i][j] != B[i][j]):
            A = function(A,i,j)
            count += 1
        else:
            continue

        if (A == B):
            print(count)
            exit()

print(-1)
</code></pre>

