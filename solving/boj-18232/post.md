[문제 바로가기](https://boj.kr/18232)

```c++
#include  <bits/stdc++.h>

using namespace std;

int visitCnt[300001];
vector<int> tp[300001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, S, E;
    cin >> N >> M >> S >> E;

    for(int i = 0; i < M; i++){
        int X, Y;
        cin >> X >> Y;
        tp[X].push_back(Y);
        tp[Y].push_back(X);
    }

    queue<int> bfsQ;
    bfsQ.push(S);
    visitCnt[S] = 1;
    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        if(cur == E){
            cout << visitCnt[cur] - 1 << "\n";
            return 0;
        }

        for(int i = 0; i < tp[cur].size(); i++){
            int next = tp[cur][i];

            if(visitCnt[next] == 0){
                bfsQ.push(next);
                visitCnt[next] = visitCnt[cur] + 1;
            }
        }

        if(cur - 1 >= 0 && visitCnt[cur - 1] == 0){
            bfsQ.push(cur - 1);
            visitCnt[cur - 1] = visitCnt[cur] + 1;
        }

        if(cur + 1 <= N && visitCnt[cur + 1] == 0){
            bfsQ.push(cur + 1);
            visitCnt[cur + 1] = visitCnt[cur] + 1;
        }
    }

    cout << -1 << "\n";

    return 0;
}

```