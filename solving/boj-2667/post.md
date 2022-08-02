[문제 바로가기](https://boj.kr/2667)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

bool isVisit[26][26];
int N, cnt;
int apt[26][26];
queue<pair<int, int>> bfsQ;
vector<pair<int, int>> tempV;

int main(){
    cin >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < N; j++){
            apt[i][j] = input[j] - '0';
            
            if(apt[i][j] == 1){
                tempV.push_back(make_pair(i, j));
            }
        }
    }

    vector<int> apts;
    for(int i = 0; i < tempV.size(); i++){
        int tempX = tempV[i].first;
        int tempY = tempV[i].second;
        if(!isVisit[tempX][tempY]){
            bfsQ.push(tempV[i]);
            cnt = 1;
            bfs();
            apts.push_back(cnt);
        }
    }

    cout << apts.size() << "\n";
    sort(apts.begin(), apts.end());
    for(int i = 0; i < apts.size(); i++){
        cout << apts[i] << "\n";
    }

    return 0;
}

void bfs(){
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();
        isVisit[curX][curY] = true;

        int dx[] = {-1, 0, 1, 0};
        int dy[] = {0, -1, 0, 1};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX >= 0 && newX < N && newY >= 0 && newY < N){
                if(!isVisit[newX][newY] && apt[newX][newY] == 1){
                    bfsQ.push(make_pair(newX, newY));
                    cnt++;
                    isVisit[newX][newY] = true;
                }
            }
        }
    }
}```