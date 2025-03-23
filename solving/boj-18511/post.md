[문제 바로가기](https://boj.kr/18511)

```c++
#include <bits/stdc++.h>

using namespace std;

long long N, K;
long long arr[3];
long long ans;

void dfs(long long cur) {
    if(cur > N){
        return;
    }

    ans = max(ans, cur);
    for(int i = 0; i < K; i++){
        dfs(cur * 10 + arr[i]);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> K;

    for(int i = 0; i < K; i++){
        cin >> arr[i];
    }

    dfs(0);

    cout << ans << "\n";

    return 0;
}
```