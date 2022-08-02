[문제 바로가기](https://boj.kr/1167)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int, int);

bool isVisit[100001];
int N, maxEnd, result;
vector<pair<int, int>> tree[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;
    for(int i = 0; i < N; i++){
        int from, to, weight;
        cin >> from;

        cin >> to;
        while(to > 0){
            cin >> weight;
            tree[from].push_back(make_pair(to, weight));

            cin >> to;
        }
    }

    dfs(1, 0);
    
    memset(isVisit, false, 100001);
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