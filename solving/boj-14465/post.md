[문제 바로가기](https://boj.kr/14465)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K, B;
    cin >> N >> K >> B;

    vector<int> sum(N + 1);
    for(int i = 0; i < B; i++){
        int temp;
        cin >> temp;
        sum[temp] = 1;
    }

    for(int i = 1; i <= N; i++){
        sum[i] += sum[i - 1];
    }

    int ans = B;
    for(int i = 1; i <= N - K + 1; i++){
        ans = min(sum[i + K - 1] - sum[i - 1], ans);
    }

    cout << ans << "\n";

    return 0;
}```