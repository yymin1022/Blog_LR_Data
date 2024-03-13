[문제 바로가기](https://boj.kr/24445)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, R;
    cin >> N >> M >> R;

    vector<vector<int>> arr(N + 1);
    for(int i = 0; i < M; i++){
        int U, V;
        cin >> U >> V;
        arr[U].push_back(V);
        arr[V].push_back(U);
    }

    for(int i = 1; i <= N; i++){
        sort(arr[i].begin(), arr[i].end(), greater<int>());
    }

    queue<int> bfsQ;
    bfsQ.push(R);

    vector<int> ans(N + 1, 0);
    ans[R] = 1;
    int cnt = 2;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 0; i < arr[cur].size(); i++){
            int next = arr[cur][i];
            if(!ans[next]){
                ans[next] = cnt;
                bfsQ.push(next);
                cnt++;
            }
        }
    }

    for(int i = 1; i <= N; i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```