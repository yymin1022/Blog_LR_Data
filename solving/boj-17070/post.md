[문제 바로가기](https://boj.kr/17070)

```c++
#include <bits/stdc++.h>

using namespace std;

bool check(int, int);

int dp[3][20][20];
int house[20][20];
int N;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            cin >> house[i][j];
        }
    }

    dp[0][1][2] = 1;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            if(check(i, j - 1) && check(i, j)){
                dp[0][i][j] += dp[0][i][j - 1] + dp[2][i][j - 1];
            }
            if(check(i - 1, j) && check(i, j)){
                dp[1][i][j] += dp[1][i - 1][j] + dp[2][i - 1][j];
            }
            if(check(i - 1, j - 1) && check(i - 1, j) && check(i, j - 1) && check(i, j)){
                dp[2][i][j] += dp[0][i - 1][j - 1] + dp[1][i - 1][j - 1] + dp[2][i - 1][j - 1];
            }
        }
    }

    int answer = dp[0][N][N] + dp[1][N][N] + dp[2][N][N];
    cout << answer << "\n";

    return 0;
}

bool check(int x, int y){
    if(x > 0 && x <= N && y > 0 && y <= N && house[x][y] == 0){
        return true;
    }
    return false;
}```