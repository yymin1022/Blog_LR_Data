[문제 바로가기](https://boj.kr/10826)

```python
arr = [0, 1]
N = int(input())

for i in range(2, N + 1):
    arr.append(arr[i - 1] + arr[i - 2])

print(arr[N])
```