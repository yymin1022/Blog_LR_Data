[문제 바로가기](https://boj.kr/7579)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> memory;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        memory.push_back(input);
    }

    int costSum = 0;
    vector<int> cost;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        cost.push_back(input);
        costSum += input;
    }

    for(int i = 0; i < N; i++){
        for(int j = costSum; j >= cost[i]; j--){
            dp[j] = max(dp[j - cost[i]] + memory[i], dp[j]);
        }
    }

    int ans = 0;
    for(int i = 0; i < 10001; i++){
        if(dp[i] >= M){
            break;
        }
        ans++;
    }

    cout << ans << "\n";

    return 0;
}

```