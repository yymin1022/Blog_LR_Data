[문제 바로가기](https://boj.kr/1865)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, M, W;
        cin >> N >> M >> W;

        vector<vector<pair<int, int>>> E(N + 1);
        for(int i = 0; i < M; i++){
            int s, e, t;
            cin >> s >> e >> t;

            E[s].push_back(make_pair(e, t));
            E[e].push_back(make_pair(s, t));
        }

        for(int i = 0; i < W; i++){
            int s, e, t;
            cin >> s >> e >> t;

            E[s].push_back(make_pair(e, t * -1));
        }

        bool isMinus = false;
        vector<int> dist(N + 1, 987654321);
        for(int k = 0; k < N; k++){
            for(int i = 1; i <= N; i++){
                for(int j = 0; j < E[i].size(); j++){
                    int toGo = E[i][j].first;
                    int cost = E[i][j].second;

                    if(dist[toGo] > dist[i] + cost){
                        dist[toGo] = dist[i] + cost;

                        if(k == N - 1){
                            isMinus = true;
                        }
                    }
                }
            }
        }

        if(isMinus){
            cout << "YES" << "\n";
        }else{
            cout << "NO" << "\n";
        }
    }

    return 0;
}
```