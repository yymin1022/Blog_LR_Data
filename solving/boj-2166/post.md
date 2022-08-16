[문제 바로가기](https://boj.kr/2166)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<long long, long long>> point;
    for(int i = 0; i < N; i++){
        long long x, y;
        cin >> x >> y;
        point.push_back(make_pair(x, y));
    }

    long long sum = point[0].first * point[N - 1].second - point[N - 1].first * point[0].second;
    for(int i = 1; i < N; i++){
        sum += point[i].first * point[i - 1].second - point[i - 1].first * point[i].second;
    }

    cout << fixed;
    cout.precision(1);
    cout << (double)(abs(sum) / 2.0) << "\n";

    return 0;
}
```