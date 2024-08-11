[문제 바로가기](https://boj.kr/7515)

```python
dp = [1, 1]
for i in range(2, 50):
    dp.append(dp[i - 1] + dp[i - 2])

N = int(input())

for i in range(0, N):
    S = int(input())

    print(f"Scenario {i + 1}:\n{dp[S + 1]}\n")
```