[문제 바로가기](https://boj.kr/16502)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M;
double ans[4];
vector<pair<int, double>> arr[4];

void dfs(int cur, double sum, int cnt){
    if(cnt == N){
        ans[cur] += sum * 100;
        return;
    }

    for(int i = 0; i < arr[cur].size(); i++){
        pair<int, double> next = arr[cur][i];
        dfs(next.first, next.second * sum, cnt + 1);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        char from, to;
        double val;
        cin >> from >> to >> val;

        arr[from - 'A'].push_back(make_pair(to - 'A', val));
    }

    for(int i = 0; i < 4; i++){
        dfs(i, 0.25, 0);
    }

    cout << fixed;
    cout.precision(3);
    for(int i = 0; i < 4; i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```
