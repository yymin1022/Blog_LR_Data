[문제 바로가기](https://boj.kr/11724)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int);

bool isVisit[1001];
int N, M, cnt;
int graph[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int from, to;
        cin >> from >> to;
        graph[from][to] = 1;
        graph[to][from] = 1;
    }

    for(int i = 1; i <= N; i++){
        if(!isVisit[i]){
            dfs(i);
            cnt++;
        }
    }

    cout << cnt << "\n";

    return 0;
}

void dfs(int n){
    for(int i = 1; i <= N; i++){
        if(!isVisit[i] && (graph[n][i] == 1 || graph[i][n] == 1)){
            isVisit[i] = true;
            dfs(i);
        }
    }
}
```