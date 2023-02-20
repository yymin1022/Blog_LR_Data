[문제 바로가기](https://boj.kr/2740)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, M, K;
    int matrix1[101][101];
    int matrix2[101][101];
    
    cin >> N >> M;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> matrix1[i][j];
        }
    }

    cin >> M >> K;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < K; j++){
            cin >> matrix2[i][j];
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < K; j++){
            int tmp = 0;
            for(int k = 0; k < M; k++){
                tmp += matrix1[i][k] * matrix2[k][j];
            }
            cout << tmp << " ";
        }
        cout << "\n";
    }
    
    return 0;
}
```