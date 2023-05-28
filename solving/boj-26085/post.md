[문제 바로가기](https://boj.kr/26085)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1001][1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> cnt(2, 0);
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> arr[i][j];
            cnt[arr[i][j]]++;
        }
    }

    if(cnt[0] % 2 || cnt[1] % 2){
        cout << -1 << "\n";
        return 0;
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            int dx[4] = {0, 1, 0, -1};
            int dy[4] = {1, 0, -1, 0};
            for(int k = 0; k < 4; k++){
                int x = i + dx[k];
                int y = j + dy[k];

                if(x < 0 || x >= N || y < 0 || y >= M){
                    continue;
                }

                if(arr[i][j] == arr[x][y]){
                    cout << 1 << "\n";
                    return 0;
                }
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}

```