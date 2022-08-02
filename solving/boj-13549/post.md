[문제 바로가기](https://boj.kr/13549)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    queue<pair<int, int>> bfs;
    vector<bool> isVisit(100999, false);
    bfs.push(make_pair(N, 0));
    isVisit[N] = true;

    while(!bfs.empty()){
        int curLoc = bfs.front().first;
        int curTime = bfs.front().second;
        bfs.pop();
        isVisit[curLoc] = true;

        if(curLoc == K){
            cout << curTime << "\n";
            return 0;
        }

        if(curLoc * 2 <= 100999 && !isVisit[curLoc * 2]){
            bfs.push(make_pair(curLoc * 2, curTime));
        }
        if(curLoc - 1 >= 0 && !isVisit[curLoc - 1]){
            bfs.push(make_pair(curLoc - 1, curTime + 1));
        }
        if(curLoc + 1 <= 100999 && !isVisit[curLoc + 1]){
            bfs.push(make_pair(curLoc + 1, curTime + 1));
        }
    }

    return 0;
}```