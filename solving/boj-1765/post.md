[문제 바로가기](https://boj.kr/1765)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M;
bool isVisit[1001];
vector<int> enemy[1001];
vector<int> friends[1001];

void dfs(int idx){
    isVisit[idx] = true;

    for(int i = 0; i < friends[idx].size(); i++){
        int next = friends[idx][i];
        if(!isVisit[next]){
            dfs(next);
        }
    }

    for(int i = 0; i < enemy[idx].size(); i++){
        int tmp = enemy[idx][i];
        for(int j = 0; j < enemy[tmp].size(); j++){
            int next = enemy[tmp][j];
            if(!isVisit[next]){
                dfs(next);
            }
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        char EF;
        int P, Q;
        cin >> EF >> P >> Q;

        if(EF == 'E'){
            enemy[P].push_back(Q);
            enemy[Q].push_back(P);
        }else{
            friends[P].push_back(Q);
            friends[Q].push_back(P);
        }
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        if(!isVisit[i]){
            dfs(i);
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```