[문제 바로가기](https://boj.kr/11657)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dist[501];
vector<pair<int, int>> arr[501];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        dist[i] = 987654321;
    }

    for(int i = 0; i < M; i++){
        int A, B, C;
        cin >> A >> B >> C;
        arr[A].push_back(make_pair(B, C));
    }

    bool flag = false;
    dist[1] = 0;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            for(int k = 0; k < arr[j].size(); k++){
                int curCost = arr[j][k].second;
                int curNode = arr[j][k].first;

                if(dist[j] != 987654321 && dist[curNode] > dist[j] + curCost){
                    dist[curNode] = dist[j] + curCost;
                    if(i == N){
                        flag = true;
                    }
                }
            }
        }
    }

    if(flag){
        cout << -1 << "\n";
    }else{
        for(int i = 2; i <= N; i++){
            if(dist[i] >= 987654321){
                cout << -1 << "\n";
            }else{
                cout << dist[i] << "\n";
            }
        }
    }

    return 0;
}
```