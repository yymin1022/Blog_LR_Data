[문제 바로가기](https://boj.kr/24480)

```c++
#include  <bits/stdc++.h>

using namespace std;

int ans[100001];
vector<int> arr[100001];

int cnt = 1;
void dfs(int cur){
    ans[cur] = cnt;
    cnt++;

    for(int i = 0; i < arr[cur].size(); i++){
        int next = arr[cur][i];
        if(!ans[next]){
            dfs(next);
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, R;
    cin >> N >> M >> R;

    for(int i = 0; i < M; i++){
        int U, V;
        cin >> U >> V;
        arr[U].push_back(V);
        arr[V].push_back(U);
    }

    for(int i = 1; i <= N; i++){
        sort(arr[i].begin(), arr[i].end(), greater<int>());
    }

    dfs(R);

    for(int i = 1; i <= N; i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```