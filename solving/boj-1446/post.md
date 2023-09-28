[문제 바로가기](https://boj.kr/1446)

```c++
#include <bits/stdc++.h>

using namespace std;

int dist[10001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, D;
    cin >> N >> D;

    vector<pair<int, int>> route[10001];
    for(int i = 0; i < N; i++){
        int A, B, C;
        cin >> A >> B >> C;

        if(B <= D && C < B - A){
            route[A].push_back(make_pair(B, C));
        }
    }

    for(int i = 0; i <= D; i++){
        dist[i] = i;
    }

    for(int i = 0; i <= D; i++){
        if(i > 0){
            dist[i] = min(dist[i - 1] + 1, dist[i]);
        }
        for(int j = 0; j < route[i].size(); j++){
            if(route[i][j].first <= D){
                dist[route[i][j].first] = min(dist[i] + route[i][j].second, dist[route[i][j].first]);
            }
        }
    }

    cout << dist[D] << "\n";

    return 0;
}
```