[문제 바로가기](https://boj.kr/1967)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int, int);

bool isVisit[10001];
int N, maxEnd, result;
vector<pair<int, int>> tree[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;
    for(int i = 0; i < N - 1; i++){
        int from, to, weight;
        cin >> from >> to >> weight;
        tree[from].push_back(make_pair(to, weight));
        tree[to].push_back(make_pair(from, weight));
    }

    dfs(1, 0);
    
    memset(isVisit, false, 10001);
    result = 0;
    dfs(maxEnd, 0);

    cout << result << "\n";
    
    return 0;
}

void dfs(int start, int length){
    if(isVisit[start]){
        return;
    }

    isVisit[start] = true;
    if(result < length){
        maxEnd = start;
        result = length;
    }

    for(int i = 0; i < tree[start].size(); i++){
        dfs(tree[start][i].first, length + tree[start][i].second);
    }
}```