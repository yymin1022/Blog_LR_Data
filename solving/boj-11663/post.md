[문제 바로가기](https://boj.kr/11663)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> points;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        points.push_back(input);
    }

    sort(points.begin(), points.end());

    for(int i = 0; i < M; i++){
        int L, R;
        cin >> L >> R;

        int left = lower_bound(points.begin(), points.end(), L) - points.begin();
        int right = upper_bound(points.begin(), points.end(), R) - points.begin();
        cout << right - left << "\n";
    }

    return 0;
}
```