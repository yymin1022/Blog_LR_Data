[문제 바로가기](https://boj.kr/24444)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[100001];
int ans[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, R;
    cin >> N >> M >> R;

    vector<int> arr[100001];
    for(int i = 0; i < M; i++){
        int u, v;
        cin >> u >> v;
        arr[u].push_back(v);
        arr[v].push_back(u);
    }

    for(int i = 0; i < N; i++){
        sort(arr[i].begin(), arr[i].end());
    }

    queue<int> bfsQ;
    bfsQ.push(R);
    int cnt = 1;
    ans[R] = cnt;
    isVisit[R] = true;
    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 0; i < arr[cur].size(); i++){
            int next = arr[cur][i];
            if(!isVisit[next]){
                cnt++;
                ans[next] = cnt;
                bfsQ.push(next);
                isVisit[next] = true;
            }
        }
    }

    for(int i = 1; i <= N; i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```