[문제 바로가기](https://boj.kr/4485)

```c++
#include <bits/stdc++.h>

using namespace std;

int dijkstra();

int N;

int dist[130][130];
int rupee[130][130];

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    cin >> N;

    int cnt = 1;
    while(N){
        for(int i = 0; i < N; i++){
            for(int j = 0; j < N; j++){
                cin >> rupee[i][j];
            }
        }

        cout << "Problem " << cnt << ": " << dijkstra() << "\n";

        cin >> N;
        cnt++;
    }

    return 0;
}

int dijkstra(){
    for(int i = 0; i < 130; i++){
        for(int j = 0; j < 130; j++){
            dist[i][j] = 987654321;
        }
    }

    priority_queue<pair<int, pair<int, int>>> pq;
    pq.push(make_pair(rupee[0][0] * -1, make_pair(0, 0)));
    dist[0][0] = rupee[0][0];

    while(!pq.empty()){
        int curX = pq.top().second.first;
        int curY = pq.top().second.second;
        int curD = pq.top().first * -1;
        pq.pop();

        int dx[4] = {-1, 0, 1, 0};
        int dy[4] = {0, 1, 0, -1};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];
            int newD = curD + rupee[newX][newY];

            if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                continue;
            }

            if(newD < dist[newX][newY]){
                dist[newX][newY] = newD;
                pq.push(make_pair(newD * -1, make_pair(newX, newY)));
            }
        }
    }

    return dist[N - 1][N - 1];
}```