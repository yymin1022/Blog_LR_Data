[문제 바로가기](https://boj.kr/1525)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string current;
    string result = "123456780";
    for(int i = 0; i < 9; i++){
        char input;
        cin >> input;
        current.push_back(input);
    }

    queue<pair<string, int>> bfsQ;
    set<string> visitStr;

    bfsQ.push(make_pair(current, 0));
    visitStr.insert(current);

    while(!bfsQ.empty()){
        int curTime = bfsQ.front().second;
        string curStr = bfsQ.front().first;
        bfsQ.pop();

        if(curStr == result){
            cout << curTime << "\n";
            return 0;
        }

        int idxZero = curStr.find('0');
        int curX = idxZero / 3;
        int curY = idxZero % 3;

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= 3 || newY < 0 || newY >= 3){
                continue;
            }

            string nextStr = curStr;
            swap(nextStr[curX * 3 + curY], nextStr[newX * 3 + newY]);

            if(visitStr.find(nextStr) == visitStr.end()){
                bfsQ.push(make_pair(nextStr, curTime + 1));
                visitStr.insert(nextStr);
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}
```