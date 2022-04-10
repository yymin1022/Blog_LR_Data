### 프로그래머스 42576. 완주하지 못한 선수

[문제 바로가기](https://programmers.co.kr/learn/courses/30/lessons/42576)

```python
def solution(participant, completion):
    answer = ''
    participant.sort()
    completion.sort()
    
    for i in range(len(participant)):
        if participant[i - 1] != completion[i - 1]:
            return participant[i - 1]
```