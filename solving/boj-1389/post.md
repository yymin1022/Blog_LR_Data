[문제 바로가기](https://boj.kr/1389)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs(int);

bool isVisit[101][101];
int friends[101];
int relation[101][101];
int cmp = 987654321;
int answer = 0;
int M, N;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int a, b;
        cin >> a >> b;
        relation[a][b] = 1;
        relation[b][a] = 1;
    }

    for(int i = 1; i <= N; i++){
        bfs(i);
        if(cmp > friends[i]){
            answer = i;
            cmp = friends[i];
        }
    }

    cout << answer << "\n";

    return 0;
}

void bfs(int from){
    queue<int> bfsQ;
    bfsQ.push(from);
    isVisit[from][from] = true;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 1; i <= N; i++){
            if(!isVisit[from][i] && relation[cur][i] == 1){
                bfsQ.push(i);
                relation[from][i] = relation[from][cur] + relation[cur][i];
                isVisit[from][i] = true;
                friends[from] += relation[from][i];
            }
        }
    }
}```