[문제 바로가기](https://boj.kr/2644)

```c++
#include <bits/stdc++.h>

using namespace std;

int bfs();

bool isVisit[101];
int N, M, A, B;

queue<pair<int, int>> bfsQ;
vector<int> family[101];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> A >> B >> M;

    for(int i = 0; i < M; i++){
        int X, Y;
        cin >> X >> Y;
        family[X].push_back(Y);
        family[Y].push_back(X);
    }

    bfsQ.push(make_pair(A, 0));
    isVisit[A] = true;

    cout << bfs() << "\n";

    return 0;
}

int bfs(){
    while(!bfsQ.empty()){
        int curIdx = bfsQ.front().first;
        int curCnt = bfsQ.front().second;
        bfsQ.pop();

        if(curIdx == B){
            return curCnt;
        }

        for(int i = 0; i < family[curIdx].size(); i++){
            int next = family[curIdx][i];

            if(!isVisit[next]){
                bfsQ.push(make_pair(next, curCnt + 1));
                isVisit[next] = true;
            }
        }
    }

    return -1;
}```