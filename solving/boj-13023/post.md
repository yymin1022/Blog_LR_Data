[문제 바로가기](https://boj.kr/13023)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[2001];
int N, M;
vector<int> relative[2002];

bool dfs(int cur, int idx){
    isVisit[cur] = true;
    if(idx == 4){
        return true;
    }

    for(int i = 0; i < relative[cur].size(); i++){
        if(!isVisit[relative[cur][i]]){
            if(dfs(relative[cur][i], idx + 1)){
                return true;
            }
        }
    }

    isVisit[cur] = false;
    return false;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int a, b;
        cin >> a >> b;
        relative[a].push_back(b);
        relative[b].push_back(a);
    }

    for(int i = 0; i < N; i++){
        fill(isVisit, isVisit + N, false);
        if(dfs(i, 0)){
            cout << 1 << "\n";
            return 0;
        }
    }

    cout << 0 << "\n";

    return 0;
}
```