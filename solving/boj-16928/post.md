[문제 바로가기](https://boj.kr/16928)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

bool isVisit[101];
int M, N;
int cnt[101];
int ladder[101];
int snake[101];
queue<int> bfsQ;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        int from, to;
        cin >> from >> to;
        ladder[from] = to;
    }
    for(int i = 0; i < M; i++){
        int from, to;
        cin >> from >> to;
        snake[from] = to;
    }

    bfsQ.push(1);
    isVisit[1] = true;

    bfs();

    cout << cnt[100] << "\n";

    return 0;
}

void bfs(){
    while(!bfsQ.empty()){
        int current = bfsQ.front();
        bfsQ.pop();

        for(int i = 1; i <= 6; i++){
            int temp = current + i;
            if(temp <= 100){
                temp = (ladder[temp] != 0) ? ladder[temp] : temp;
                temp = (snake[temp] != 0) ? snake[temp] : temp;

                if(!isVisit[temp]){
                    cnt[temp] = cnt[current] + 1;
                    isVisit[temp] = true;
                    bfsQ.push(temp);
                }
            }
        }
    }
}```