### 프로그래머스 42839. 소수찾기

[문제 바로가기](https://programmers.co.kr/learn/courses/30/lessons/42839)

```python
from itertools import permutations
from math import sqrt

def isPrime(num):
    if num == 0 or num == 1:
        return False
    
    if num == 2:
        return True
    
    for i in range(int(sqrt(num))):
        if num % (i + 2) == 0:
            return False

    return True

def solution(numbers):
    answer = 0
    primeList = []

    for i in range(len(numbers)):
        permulist = list(map(''.join, permutations(list(numbers), i + 1)))
        for i in list(set(permulist)):
            if isPrime(int(i)):
                primeList.append(int(i))
    
    answer = len(set(primeList))
    
    return answer
```