[문제 바로가기](https://boj.kr/1325)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[10001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> hack[10001];
    for(int i = 0; i < M; i++){
        int a, b;
        cin >> a >> b;
        hack[b].push_back(a);
    }

    int maxCnt = 0;
    vector<int> ans(N + 1);
    for(int i = 1; i <= N; i++){
        memset(isVisit, false, sizeof(isVisit));
        queue<int> bfsQ;
        bfsQ.push(i);
        isVisit[i] = true;

        int cnt = 0;
        while(!bfsQ.empty()){
            int cur = bfsQ.front();
            bfsQ.pop();
            cnt++;

            for(int j : hack[cur]){
                if(!isVisit[j]){
                    bfsQ.push(j);
                    isVisit[j] = true;
                }
            }
        }

        ans[i] = cnt;
        maxCnt = max(cnt, maxCnt);
    }

    for(int i = 1; i <= N; i++){
        if(ans[i] == maxCnt){
            cout << i << " ";
        }
    }
}
```