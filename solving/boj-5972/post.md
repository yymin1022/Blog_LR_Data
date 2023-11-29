[문제 바로가기](https://boj.kr/5972)

```c++
#include <bits/stdc++.h>

using namespace std;

int dist[500001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<int, int>> arr[50001];
    for(int i = 0; i < M; i++){
        int A, B, C;
        cin >> A >> B >> C;
        arr[A].push_back(make_pair(B, C));
        arr[B].push_back(make_pair(A, C));
    }

    for(int i = 0; i <= N; i++){
        dist[i] = 987654321;
    }

    priority_queue<pair<int, int>> pq;
    pq.push(make_pair(1, 0));
    dist[1] = 0;
    while(!pq.empty()){
        int cur = pq.top().first;
        int curCost = -pq.top().second;
        pq.pop();

        for(int i = 0; i < arr[cur].size(); i++){
            int next = arr[cur][i].first;
            int nextCost = arr[cur][i].second + curCost;

            if(nextCost < dist[next]){
                dist[next] = nextCost;
                pq.push(make_pair(next, -nextCost));
            }
        }
    }

    cout << dist[N] << "\n";

    return 0;
}

```
