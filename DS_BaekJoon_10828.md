## 접근방식
스택은 리스트로 구현했고 pop은 파이썬 내장함수를 이용했다.


## 코드
<pre><code>
N = int(input())
stack = []
output_array = []

for _ in range(N):
    command = input()
    if ("push" in command):
        stack.append(int((command.split())[1]))
    elif (command == "pop"):
        if (len(stack) == 0):
            output_array.append(-1)
        else:
            value = stack.pop()
            output_array.append(value)
    elif (command == "size"):
        output_array.append(len(stack))
    elif (command == "empty"):
        if (len(stack) == 0):
            output_array.append(1)
        else:
            output_array.append(0)
    else:
        if (len(stack) == 0):
            output_array.append(-1)
        else:
            output_array.append(stack[-1])

for i in output_array:
    print(i)
</code></pre>
