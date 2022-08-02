[문제 바로가기](https://boj.kr/2167)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[301][301];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= M; j++){
            int input;
            cin >> input;
            arr[i][j] = arr[i][j - 1] + arr[i - 1][j] - arr[i - 1][j - 1] + input;
        }
    }

    int K;
    cin >> K;

    for(int h = 0; h < K; h++){
        int i, j, x, y;
        cin >> i >> j >> x >> y;
        cout << arr[x][y] - arr[x][j - 1] - arr[i - 1][y] + arr[i - 1][j - 1] << "\n";
    }



    return 0;
}```