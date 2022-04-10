[문제 바로가기](https://boj.kr/1260)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs(int);
void dfs(int);

bool isVisit[1001];
vector<int> graph[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int N, M, V;
    cin >> N >> M >> V;

    for(int i = 0; i < M; i++){
        int s, d;
        cin >> s >> d;

        graph[s].push_back(d);
        graph[d].push_back(s);
    }

    for(int i = 1; i <= N; i++){
        sort(graph[i].begin(), graph[i].end());
    }

    dfs(V);
    cout << "\n";
    bfs(V);
    
    return 0;
}

void bfs(int start){
    memset(isVisit, false, sizeof(isVisit));
    queue<int> bfsQueue;

    bfsQueue.push(start);
    isVisit[start] = true;

    while(!bfsQueue.empty()){
        int current = bfsQueue.front();
        bfsQueue.pop();
        cout << current << " ";

        for(int i = 0; i < graph[current].size(); i++){
            int next = graph[current][i];
            if(!isVisit[next]){
                bfsQueue.push(next);
                isVisit[next] = true;
            }
        }
    }
}

void dfs(int current){
    isVisit[current] = true;
    cout << current << " ";

    for(int i = 0; i < graph[current].size(); i++){
        int next = graph[current][i];
        if(!isVisit[next]){
            dfs(next);
        }
    }
}
```