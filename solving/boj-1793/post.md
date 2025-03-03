[문제 바로가기](https://boj.kr/1793)

```python3
dp = [1, 1, 3]
for i in range(3, 251):
    dp.append(dp[i - 1] + dp[i - 2] * 2)

while True:
    try:
        N = int(input())
        print(dp[N])
    except:
        break
```