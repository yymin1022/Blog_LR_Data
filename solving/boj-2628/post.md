[문제 바로가기](https://boj.kr/2628)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int W, H, N;
    cin >> W >> H >> N;

    vector<int> cut[2];
    cut[0].push_back(H);
    cut[1].push_back(W);
    for(int i = 0; i < N; i++){
        int X, Y;
        cin >> X >> Y;
        cut[X].push_back(Y);
    }

    sort(cut[0].begin(), cut[0].end());
    sort(cut[1].begin(), cut[1].end());

    int ans[2] = {cut[0][0], cut[1][0]};
    for(int i = 1; i < cut[0].size(); i++){
        ans[0] = max(cut[0][i] - cut[0][i - 1], ans[0]);
    }
    for(int i = 1; i < cut[1].size(); i++){
        ans[1] = max(cut[1][i] - cut[1][i - 1], ans[1]);
    }

    cout << ans[0] * ans[1] << "\n";

    return 0;
}
```