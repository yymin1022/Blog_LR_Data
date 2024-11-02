[문제 바로가기](https://boj.kr/21735)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M, ans;
vector<int> arr;

void dfs(int cur, int size, int cnt){
    if(cnt == M || cur >= N){
        ans = max(size, ans);
        return;
    }

    dfs(cur + 1, size + arr[cur + 1], cnt + 1);
    dfs(cur + 2, size / 2 + arr[cur + 2], cnt + 1);
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    dfs(-1, 1, 0);

    cout << ans << "\n";

    return 0;
}

```
