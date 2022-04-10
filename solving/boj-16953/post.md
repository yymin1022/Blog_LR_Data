[문제 바로가기](https://boj.kr/16953)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

long long A, B;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> A >> B;

    bfs();

    return 0;
}

void bfs(){
    bool isDone = false;
    queue<pair<long long, long long>> bfsQ;
    bfsQ.push(make_pair(A, 1));

    while(!bfsQ.empty()){
        long long curNum = bfsQ.front().first;
        long long curCnt = bfsQ.front().second;
        bfsQ.pop();

        if(curNum == B){
            cout << curCnt << "\n";
            isDone = true;
            break;
        }

        long long temp;
        curCnt++;
        temp = curNum * 2;
        if(temp <= B){
            bfsQ.push(make_pair(temp, curCnt));
        }
        temp = curNum * 10 + 1;
        if(temp <= B){
            bfsQ.push(make_pair(temp, curCnt));
        }
    }

    if(!isDone){
        cout << -1 << "\n";
    }
}
```