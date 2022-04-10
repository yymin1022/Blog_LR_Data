[문제 바로가기](https://boj.kr/9019)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

bool isDone[10001];
int A, B;
queue<pair<int, string>> bfsQ;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        cin >> A >> B;
        bfsQ.push(make_pair(A, ""));
        bfs();
    }

    return 0;
}

void bfs(){
    while(!bfsQ.empty()){
        int curNum = bfsQ.front().first;
        string curCmd = bfsQ.front().second;
        bfsQ.pop();

        if(curNum == B){
            cout << curCmd << "\n";

            memset(isDone, false, sizeof(isDone));
            while(!bfsQ.empty()){
                bfsQ.pop();
            }
            break;
        }

        int newNum;
        string newCmd;

        newNum = (curNum * 2) % 10000;
        newCmd = curCmd + "D";
        if(!isDone[newNum]){
            bfsQ.push(make_pair(newNum, newCmd));
            isDone[newNum] = true;
        }

        newNum = (curNum != 0) ? curNum - 1 : 9999;
        newCmd = curCmd + "S";
        if(!isDone[newNum]){
            bfsQ.push(make_pair(newNum, newCmd));
            isDone[newNum] = true;
        }

        newNum = (curNum % 1000) * 10 + (curNum / 1000);
        newCmd = curCmd + "L";
        if(!isDone[newNum]){
            bfsQ.push(make_pair(newNum, newCmd));
            isDone[newNum] = true;
        }

        newNum = (curNum / 10) + (curNum % 10) * 1000;
        newCmd = curCmd + "R";
        if(!isDone[newNum]){
            bfsQ.push(make_pair(newNum, newCmd));
            isDone[newNum] = true;
        }
    }
}
```