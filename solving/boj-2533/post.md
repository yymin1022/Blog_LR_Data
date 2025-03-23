[문제 바로가기](https://boj.kr/2533)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[1000001];
int dp[1000001][2];
vector<int> sns[1000001];

void dfs(int cur){
    isVisit[cur] = true;

    dp[cur][0] = 1;
    for(int i = 0; i < sns[cur].size(); i++){
        int next = sns[cur][i];

        if(!isVisit[next]){
            dfs(next);
            dp[cur][0] += min(dp[next][0], dp[next][1]);
            dp[cur][1] += dp[next][0];
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N - 1; i++){
        int u, v;
        cin >> u >> v;
        sns[u].push_back(v);
        sns[v].push_back(u);
    }

    dfs(1);
    cout << min(dp[1][0], dp[1][1]) << "\n";

    return 0;
}

```