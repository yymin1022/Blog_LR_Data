[문제 바로가기](https://boj.kr/16234)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[51][51];
int country[51][51];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, L, R;
    cin >> N >> L >> R;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> country[i][j];
        }
    }

    bool isFinish = false;
    int ans = 0;
    int peopleSum = 0;
    queue<pair<int, int>> bfsQ;
    vector<pair<int, int>> moveCountry;
    while(!isFinish){
        isFinish = true;
        memset(isVisit, false, sizeof(isVisit));

        for(int i = 0; i < N; i++){
            for(int j = 0; j < N; j++){
                if(!isVisit[i][j]){
                    bfsQ.push(make_pair(i, j));
                    isVisit[i][j] = true;
                    moveCountry.clear();
                    moveCountry.push_back(make_pair(i, j));
                    peopleSum = country[i][j];

                    while(!bfsQ.empty()){
                        int curX = bfsQ.front().first;
                        int curY = bfsQ.front().second;
                        bfsQ.pop();

                        int dx[4] = {0, 1, 0, -1};
                        int dy[4] = {1, 0, -1, 0};
                        for(int i = 0; i < 4; i++){
                            int newX = curX + dx[i];
                            int newY = curY + dy[i];

                            if(newX < 0 || newX >= N || newY < 0 || newY >= N || isVisit[newX][newY]){
                                continue;
                            }

                            if(abs(country[newX][newY] - country[curX][curY]) >= L && abs(country[newX][newY] - country[curX][curY]) <= R){
                                bfsQ.push(make_pair(newX, newY));
                                isVisit[newX][newY] = true;
                                moveCountry.push_back(make_pair(newX, newY));
                                peopleSum += country[newX][newY];
                            }
                        }
                    }
                }

                if(moveCountry.size() > 1){
                    isFinish = false;
                    for(int i = 0; i < moveCountry.size(); i++){
                        country[moveCountry[i].first][moveCountry[i].second] = peopleSum / moveCountry.size();
                    }
                }
            }
        }

        if(!isFinish){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```
