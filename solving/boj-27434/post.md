[문제 바로가기](https://boj.kr/27434)

```python
N = int(input())
ans = 1
for i in range(N):
    ans = ans * N
    N -= 1
print(ans)
```