[문제 바로가기](https://boj.kr/30088)

```c++
#include <bits/stdc++.h>

using namespace std;

long long sum[1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int K;
        cin >> K;

        long long tmp = 0;
        for(int j = 0; j < K; j++){
            long long input;
            cin >> input;
            tmp += input;
        }
        sum[i] = tmp;
    }

    sort(sum, sum + N);

    long long ans = sum[0];
    for(int i = 1; i < N; i++){
        sum[i] += sum[i - 1];
        ans += sum[i];
    }

    cout << ans << "\n";

    return 0;
}
```
