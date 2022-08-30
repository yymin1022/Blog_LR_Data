[문제 바로가기](https://boj.kr/11779)

```c++
#include  <bits/stdc++.h>

using namespace std;

void dijkstra(int);

int N, M, S, E;
vector<pair<int, int>> city[1001];
vector<int> dist(1001);
vector<int> route(1001);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int from, to, cost;
        cin >> from >> to >> cost;
        city[from].push_back(make_pair(to, cost));
    }

    cin >> S >> E;

    fill(dist.begin(), dist.end(), 9876543210);
    dijkstra(S);
    route[S] = 0;

    vector<int> ans;
    int cur = E;
    while(route[cur]){
        ans.push_back(cur);
        cur = route[cur];
    }
    ans.push_back(S);

    cout << dist[E] << "\n";
    cout << ans.size() << "\n";

    for(int i = ans.size() - 1; i >= 0; i--){
        cout << ans[i] << " ";
    }

    return 0;
}

void dijkstra(int start){
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
                route[nextLocation] = curLocation;
                pq.push(make_pair(dist[nextLocation], nextLocation));
            }
        }
    }
}
```