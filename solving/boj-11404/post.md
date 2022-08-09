[문제 바로가기](https://boj.kr/11404)

```c++
#include <bits/stdc++.h>

using namespace std;

int bus[101][101];
int N, M;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            if(i != j){
                bus[i][j] = 987654321;
            }
        }
    }

    for(int i = 0; i < M; i++){
        int a, b, c;
        cin >> a >> b >> c;
        bus[a][b] = min(c, bus[a][b]);
    }

    for(int j = 1; j <= N; j++){
        for(int i = 1; i <= N; i++){
            for(int k = 1; k <= N; k++){
                bus[i][k] = min(bus[i][j] + bus[j][k], bus[i][k]);
            }
        }
    }

    for(int i = 1; i <= N; i++){
        for (int j = 1; j <= N; j++){
            if(bus[i][j] == 987654321){
                cout << 0 << " ";
            }else{
                cout << bus[i][j] << " ";
            }
        }
        cout << "\n";
    }
}
```