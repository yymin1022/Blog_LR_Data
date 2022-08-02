[문제 바로가기](https://boj.kr/12865)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[101][100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<pair<int, int>> item;
    for(int i = 0; i < N; i++){
        int value, weight;
        cin >> weight >> value;

        item.push_back(make_pair(weight, value));
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j <= K; j++){
            if(i == 0){
                if(item[i].first <= j){
                    dp[i][j] = item[i].second;
                    continue;
                }
            }else if(item[i].first <= j){
                dp[i][j] = max(dp[i - 1][j], item[i].second + dp[i - 1][j - item[i].first]);
            }else{
                dp[i][j] = dp[i - 1][j];
            }
        }
    }

    cout << dp[N - 1][K] << "\n";

    return 0;
}```