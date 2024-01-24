[문제 바로가기](https://boj.kr/2342)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[100001][5][5];

int getDistance(int X, int Y){
    if(X == 0){
        return 2;
    }else if(X == Y){
        return 1;
    }else if(X - Y == 2 || Y - X == 2){
        return 4;
    }else{
        return 3;
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 100001; i++){
        for(int j = 0; j < 5; j++){
            for(int k = 0; k < 5; k++){
                dp[i][j][k] = 987654321;
            }
        }
    }
    dp[0][0][0] = 0;

    int cnt = 1;
    while(true){
        int input;
        cin >> input;
        if(input == 0){
            cnt--;
            break;
        }

        for(int i = 0; i < 5; i++){
            for(int j = 0; j < 5; j++){
                if(dp[cnt - 1][i][j] >= 987654321){
                    continue;
                }

                dp[cnt][input][j] = min(dp[cnt][input][j], dp[cnt - 1][i][j] + getDistance(i, input));
                dp[cnt][i][input] = min(dp[cnt][i][input], dp[cnt - 1][i][j] + getDistance(j, input));
           }
        }
        cnt++;
    }

    int ans = 987654321;
    for(int i = 0; i < 5; i++){
        for(int j = 0; j < 5; j++){
            ans = min(dp[cnt][i][j], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}

```
