[문제 바로가기](https://boj.kr/1240)

```c++
#include <bits/stdc++.h>

using namespace std;

int dist[1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<int, int>> route[1001];
    for(int i = 0; i < N - 1; i++){
        int A, B, C;
        cin >> A >> B >> C;

        route[A].push_back(make_pair(B, C));
        route[B].push_back(make_pair(A, C));
    }

    for(int i = 0; i < M; i++){
        memset(dist, -1, sizeof(dist));

        int A, B;
        cin >> A >> B;

        queue<int> bfsQ;
        bfsQ.push(A);
        dist[A] = 0;

        while(!bfsQ.empty()){
            int cur = bfsQ.front();
            bfsQ.pop();

            for(int j = 0; j < route[cur].size(); j++){
                int next = route[cur][j].first;
                if(dist[next] >= 0){
                    continue;
                }

                bfsQ.push(next);
                dist[next] = dist[cur] + route[cur][j].second;
            }
        }

        cout << dist[B] << "\n";
    }

    return 0;
}
```