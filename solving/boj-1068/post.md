[문제 바로가기](https://boj.kr/1068)

```c++
#include <bits/stdc++.h>

using namespace std;

int ans, del;
vector<int> node[51];

void dfs(int startNode) {
    if(startNode == del){
        return;
    }

    if(node[startNode].empty()){
        ans++;
        return;
    }

    for(int i = 0; i < node[startNode].size(); i++){
        if(node[startNode].size() == 1 && node[startNode][i] == del){
            ans++;
        }else{
            dfs(node[startNode][i]);
        }
    }
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int root;
    for(int i = 0; i < N; i++){
        int a;
        cin >> a;

        if(a == -1){
            root = i;
            continue;
        }else{
            node[a].push_back(i);
        }
    }

    cin >> del;
    dfs(root);

    cout << ans << "\n";

    return 0;
}
```