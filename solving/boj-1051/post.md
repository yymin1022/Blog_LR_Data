[문제 바로가기](https://boj.kr/1051)

```c++
#include <bits/stdc++.h>

using namespace std;

string num[51];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        cin >> num[i];
    }

    int ans = 1;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            for(int k = 1; k < N; k++) {
                if(i + k >= N || j + k >= M){
                    break;
                }

                if (num[i][j] == num[i + k][j] && num[i + k][j] == num[i + k][j + k] && num[i + k][j + k] == num[i][j + k]) {
                    ans = max((k + 1) * (k + 1), ans);
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}

```