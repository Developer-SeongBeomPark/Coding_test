## 접근 방법
두 난쟁이의 키의 합이 '아홉 난쟁이의 키의 합 - 100' 일 때, 그 두 난쟁이를 리스트에서 제외시키고 나머지를 출력한다.



## 코드
<pre><code>
import sys

Tall_list = [int(sys.stdin.readline()) for _ in range(9)]
Tall_list.sort()
value = sum(Tall_list) - 100

for i in range(8):
    for j in range(i+1,9):
        if(Tall_list[i] + Tall_list[j] == value):
            del Tall_list[i]
            del Tall_list[j-1]
            for k in Tall_list:
                print(k)
            exit()
</code></pre>
