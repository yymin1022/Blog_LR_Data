[문제 바로가기](https://boj.kr/2212)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> sensor;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        sensor.push_back(input);
    }

    sort(sensor.begin(), sensor.end());

    vector<int> dist;
    dist.push_back(0);
    for(int i = 1; i < N; i++){
        dist.push_back(sensor[i] - sensor[i - 1]);
    }

    sort(dist.begin(), dist.end());

    int ans = 0;
    for(int i = 1; i <= N - K; i++){
        ans += dist[i];
    }

    cout << ans << "\n";

    return 0;
}
```