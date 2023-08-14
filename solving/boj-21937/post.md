[문제 바로가기](https://boj.kr/21937)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[100001];
int ans;
int X;
vector<int> work[100001];

void dfs(int cur){
    ans++;
    isVisit[cur] = true;
    for(int i = 0; i < work[cur].size(); i++){
        if(!isVisit[work[cur][i]]){
            dfs(work[cur][i]);
        }
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        work[B].push_back(A);
    }

    cin >> X;

    dfs(X);

    cout << ans - 1 << "\n";

    return 0;
}

```