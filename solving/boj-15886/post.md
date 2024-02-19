[문제 바로가기](https://boj.kr/15886)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[1001];

void dfs(int cur, string S){
    if(isVisit[cur]){
        return;
    }

    isVisit[cur] = true;
    if(S[cur] == 'E'){
        dfs(cur + 1, S);
    }else{
        dfs(cur - 1, S);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(!isVisit[i] && S[i] == 'E'){
            dfs(i, S);
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}****
```