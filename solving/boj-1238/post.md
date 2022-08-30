[문제 바로가기](https://boj.kr/1238)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dijkstra(int, int);

int N, M, X;
vector<pair<int, int>> city[1001];
vector<int> dist(1001);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M >> X;

    for(int i = 0; i < M; i++){
        int from, to, cost;
        cin >> from >> to >> cost;
        city[from].push_back(make_pair(to, cost));
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        fill(dist.begin(), dist.end(), 9876543210);
        int temp = dijkstra(i, X);

        fill(dist.begin(), dist.end(), 9876543210);
        temp += dijkstra(X, i);

        ans = max(temp, ans);
    }

    cout << ans << "\n";

    return 0;
}

int dijkstra(int start, int end){
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    pq.push({0, start});
    dist[start] = 0;

    while(!pq.empty()){
        int curCost = pq.top().first;
        int curLocation = pq.top().second;
        pq.pop();

        if(curCost > dist[curLocation]) continue;

        for(int i = 0; i < city[curLocation].size(); i++){
            int nextCost = city[curLocation][i].second;
            int nextLocation = city[curLocation][i].first;

            if(curCost + nextCost < dist[nextLocation]){
                dist[nextLocation] = curCost + nextCost;
                pq.push(make_pair(dist[nextLocation], nextLocation));
            }
        }
    }

    return dist[end];
}
```