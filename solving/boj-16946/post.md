[문제 바로가기](https://boj.kr/16946)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M;
bool isVisit[1001][1001];
int ans[1001][1001];
int orig[1001][1001];
int spaceMap[1001][1001];

int dx[4] = {0, 1, 0, -1};
int dy[4] = {1, 0, -1, 0};

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    cin >> N >> M;

    vector<pair<int, int>> space;
    vector<pair<int, int>> wall;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < M; j++){
            orig[i][j] = input[j] - '0';
            
            if(orig[i][j] == 0){
                space.push_back(make_pair(i, j));
            }else{
                wall.push_back(make_pair(i, j));
            }
        }
    }

    int spaceNum = 0;
    vector<int> spaceSize;
    for(int i = 0; i < space.size(); i++){
        if(!isVisit[space[i].first][space[i].second]){
            queue<pair<int, int>> bfsQ;
            bfsQ.push(space[i]);
            isVisit[space[i].first][space[i].second] = true;

            int cnt = 0;
            while(!bfsQ.empty()){
                int curX = bfsQ.front().first;
                int curY = bfsQ.front().second;
                bfsQ.pop();
                cnt++;
                spaceMap[curX][curY] = spaceNum;

                for(int j = 0; j < 4; j++){
                    int newX = curX + dx[j];
                    int newY = curY + dy[j];

                    if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                        continue;
                    }

                    if(!isVisit[newX][newY] && !orig[newX][newY]){
                        bfsQ.push(make_pair(newX, newY));
                        isVisit[newX][newY] = true;
                    }
                }
            }
            spaceSize.push_back(cnt);
            spaceNum++;
        }
    }

    for(int i = 0; i < wall.size(); i++){
        set<int> visitSpace;

        int curX = wall[i].first;
        int curY = wall[i].second;
        for(int j = 0; j < 4; j++){
            int newX = curX + dx[j];
            int newY = curY + dy[j];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(!orig[newX][newY]){
                visitSpace.insert(spaceMap[newX][newY]);
            }
        }

        ans[curX][curY]++;
        for(auto iter = visitSpace.begin(); iter != visitSpace.end(); iter++){
            ans[curX][curY] += spaceSize[*iter];
        }
        ans[curX][curY] %= 10;
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cout << ans[i][j];
        }
        cout << "\n";
    }

    return 0;
}

```