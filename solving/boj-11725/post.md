[문제 바로가기](https://boj.kr/11725)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int);

bool isVisit[100001];
int parent[100001];
vector<int> tree[100001];
int N;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N - 1; i++){
        int from, to;
        cin >> from >> to;

        tree[from].push_back(to);
        tree[to].push_back(from);
    }

    dfs(1);

    for(int i = 2; i <= N; i++){
        cout << parent[i] << "\n";
    }

    return 0;
}

void dfs(int num){
    isVisit[num] = true;

    for(int i = 0; i < tree[num].size(); i++){
        int newNum = tree[num][i];
        if(!isVisit[newNum]){
            parent[newNum] = num;
            dfs(newNum);
        }
    }
}
```