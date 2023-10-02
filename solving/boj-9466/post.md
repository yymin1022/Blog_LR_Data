[문제 바로가기](https://boj.kr/9466)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isTeam[100001];
bool isVisit[100001];
int arr[100001];
int cnt;

void dfs(int cur){
    isVisit[cur] = true;

    int next = arr[cur];
    if(!isVisit[next]){
        dfs(next);
    }else if(!isTeam[next]){
        cnt++;
        for(int i = next; i != cur; i = arr[i]){
            cnt++;
        }
    }
    isTeam[cur] = true;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        cnt = 0;
        memset(isTeam, false, sizeof(isTeam));
        memset(isVisit, false, sizeof(isVisit));

        int N;
        cin >> N;

        for(int i = 1; i <= N; i++){
            cin >> arr[i];
        }

        for(int i = 1; i <= N; i++){
            if(!isVisit[i]){
                dfs(i);
            }
        }

        cout << N - cnt << "\n";
    }

    return 0;
}
```