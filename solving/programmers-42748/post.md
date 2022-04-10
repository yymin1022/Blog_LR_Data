### 프로그래머스 42748. K번째 수

[문제 바로가기](https://programmers.co.kr/learn/courses/30/lessons/42748)

```python
def solution(array, commands):
    answer = []
    
    for i in range(len(commands)):
        current = array[commands[i][0] - 1:commands[i][1]]
        current.sort()
        answer.append(current[commands[i][2] - 1])
    return answer
```