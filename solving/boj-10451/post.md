[문제 바로가기](https://boj.kr/10451)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001];
int graph[1001];
int N;

void dfs(int cur){
    isVisit[cur] = true;

    if(!isVisit[graph[cur]]){
        dfs(graph[cur]);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        cin >> N;

        for(int i = 1; i <= N; i++){
            cin >> graph[i];
        }

        int ans = 0;
        memset(isVisit, false, sizeof(isVisit));
        for(int i = 1; i <= N; i++){
            if(!isVisit[i]){
                dfs(i);
                ans++;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```