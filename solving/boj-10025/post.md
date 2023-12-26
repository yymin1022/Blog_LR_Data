[문제 바로가기](https://boj.kr/10025)

```c++
#include <bits/stdc++.h>

using namespace std;

int ice[1000001];
int sum[1000001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < N; i++){
        int G, X;
        cin >> G >> X;
        ice[X] = G;
    }

    sum[0] = ice[0];
    for(int i = 1; i <= 1000000; i++){
        sum[i] = ice[i] + sum[i - 1];
    }

    if(K > 1000000){
        cout << sum[1000000] << "\n";
        return 0;
    }

    int ans = 0;
    for(int i = 0; i <= 1000000; i++){
        if(i + K <= 1000000 && i - K >= 1){
            ans = max(sum[i + K] - sum[i - K - 1], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```