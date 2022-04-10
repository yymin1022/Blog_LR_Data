### 프로그래머스 42840. 모의고사

[문제 바로가기](https://programmers.co.kr/learn/courses/30/lessons/42840)

```python
def solution(answers):
    answer = []
    stu1 = [1, 2, 3, 4, 5] * 8
    stu2 = [2, 1, 2, 3, 2, 4, 2, 5] * 5
    stu3 = [3, 3, 1, 1, 2, 2, 4, 4›, 5, 5] * 4
    
    scores = [0, 0, 0]
    
    for i in range(len(answers)):
        if answers[i] == stu1[i%len(stu1)]:
            scores[0] += 1
        if answers[i] == stu2[i%len(stu2)]:
            scores[1] += 1
        if answers[i] == stu3[i%len(stu3)]:
            scores[2] += 1
        
    scoreMax = max(scores)
    
    for i in range(len(scores)):
        if scoreMax == scores[i]:
            answer.append(i + 1)
        
    answer.sort()
    
    return answer
```