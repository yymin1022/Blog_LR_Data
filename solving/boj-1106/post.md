[문제 바로가기](https://boj.kr/1106)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[21][1101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int C, N;
    cin >> C >> N;

    vector<pair<int, int>> arr;
    arr.push_back(make_pair(0, 0));
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr.push_back(make_pair(A, B));
    }

    for(int i = 0; i < 21; i++){
        for(int j = 0; j < 1101; j++){
            dp[i][j] = 987654321;
        }
    }

    int ans = 987654321;
    for(int i = 1; i <= N; i++){
        dp[i][0] = 0;

        int a = arr[i].first;
        int b = arr[i].second;
        for(int j = 1; j < 1101; j++){
            if(j >= b){
                dp[i][j] = dp[i][j - b] + a;
            }

            dp[i][j] = min(dp[i - 1][j], dp[i][j]);
        }

        for(int j = C; j < 1101; j++){
            ans = min(dp[i][j], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```