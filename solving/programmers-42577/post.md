### 프로그래머스 42577. 전화번호 목록

[문제 바로가기](https://programmers.co.kr/learn/courses/30/lessons/42577)

```python
def solution(phone_book):
    answer = True
    
    for i in range(len(phone_book)):
        for j in range(len(phone_book)):
            if i != j and phone_book[i].startswith(phone_book[j]):
                answer = False
                return answer
    
    return answer
```