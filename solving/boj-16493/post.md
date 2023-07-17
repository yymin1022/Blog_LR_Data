[문제 바로가기](https://boj.kr/16493)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[25][205];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<int, int>> chapter;
    chapter.push_back(make_pair(0, 0));
    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        chapter.push_back(make_pair(A, B));
    }

    int ans = 0;
    for(int i = 1; i <= M; i++){
        for(int j = N; j >= 0; j--){
            if(j >= chapter[i].first){
                dp[i][j] = max(dp[i - 1][j], dp[i - 1][j - chapter[i].first] + chapter[i].second);
            }else{
                dp[i][j] = dp[i - 1][j];
            }

            ans = max(dp[i][j], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```