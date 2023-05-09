[문제 바로가기](https://boj.kr/15822)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[2001][2001];
int dp[2001][2001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> X;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        X.push_back(input);
    }
    vector<int> Y;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        Y.push_back(input);
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            arr[i][j] = (X[i] - Y[j]) * (X[i] - Y[j]);
        }
    }

    dp[0][0] = arr[0][0];
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(!i && !j){
                continue;
            }

            int dx[3] = {-1, -1, 0};
            int dy[3] = {0, -1, -1};
            int tmp = 2147483647;
            for(int k = 0; k < 3; k++){
                int newI = i + dx[k];
                int newJ = j + dy[k];

                if(newI < 0 || newI >= N || newJ < 0 || newJ >= N){
                    continue;
                }

                tmp = min(dp[newI][newJ] + arr[i][j], tmp);
            }

            dp[i][j] = tmp;
        }
    }

    cout << dp[N - 1][N - 1] << "\n";

    return 0;
}
```