[문제 바로가기](https://boj.kr/29700)

```c++
#include  <bits/stdc++.h>

using namespace std;

int theater[1001][5001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            theater[i][j] = input[j] - '0';
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M - K + 1; j++){
            if(theater[i][j] == 0){
                bool isAvail = true;
                for(int k = 0; k < K; k++){
                    if(j + k < M && theater[i][j + k] == 1){
                        isAvail = false;
                        break;
                    }
                }
                if(isAvail){\
                    ans++;
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```
