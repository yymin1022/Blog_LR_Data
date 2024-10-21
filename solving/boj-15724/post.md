[문제 바로가기](https://boj.kr/15724)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1030][1030];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    for(int i = 1; i <= R; i++){
        for(int j = 1; j <= C; j++){
            cin >> arr[i][j];
            arr[i][j] += arr[i - 1][j] + arr[i][j - 1] - arr[i - 1][j - 1];
        }
    }

    int K;
    cin >> K;
    while(K--){
        int r1, c1, r2, c2;
        cin >> r1 >> c1 >> r2 >> c2;

        cout << arr[r2][c2] - arr[r2][c1 - 1] - arr[r1 - 1][c2] + arr[r1 - 1][c1 - 1] << "\n";
    }

    return 0;
}

```