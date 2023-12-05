[문제 바로가기](https://boj.kr/2458)

```c++
#include <bits/stdc++.h>

using namespace std;

int dist[501][501];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            dist[i][j] = 987654321;
        }
    }

    for(int i = 0; i < M; i++){
        int U, V;
        cin >> U >> V;
        dist[U][V] = 1;
    }

    for(int k = 1; k <= N; k++){
        for(int i = 1; i <= N; i++){
            for(int j = 1; j <= N; j++){
                dist[i][j] = min(dist[i][k] + dist[k][j], dist[i][j]);
            }
        }
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        int cnt = 0;
        for(int j = 1; j <= N; j++){
            if(dist[i][j] != 987654321 || dist[j][i] != 987654321){
                cnt++;
            }
        }

        if(cnt == N - 1){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```