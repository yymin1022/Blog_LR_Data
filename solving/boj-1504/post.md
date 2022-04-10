[문제 바로가기](https://boj.kr/1504)

```c++
#include <bits/stdc++.h>

#define INF 987654321

using namespace std;

int dijkstra(int, int);

int N, E, v1, v2;
vector<pair<int, int>> route[801];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> E;
    for(int i = 0; i < E; i++){
        int a, b, c;
        cin >> a >> b >> c;
        route[a].push_back(make_pair(b, c));
        route[b].push_back(make_pair(a, c));
    }
    cin >> v1 >> v2;

    int answer[2];
    int distance1 = dijkstra(1, v1);
    int distance2 = dijkstra(v1, v2);
    int distance3 = dijkstra(v2, N);

    if(distance1 == INF || distance2 == INF || distance3 == INF){
        cout << -1 << "\n";
        return 0;
    }
        
    answer[0] = distance1 + distance2 + distance3;

    distance1 = dijkstra(1, v2);
    distance2 = dijkstra(v2, v1);
    distance3 = dijkstra(v1, N);

    if(distance1 == INF || distance2 == INF || distance3 == INF){
        cout << -1 << "\n";
        return 0;
    }
        
    answer[1] = distance1 + distance2 + distance3;

    cout << min(answer[0], answer[1]) << "\n";

    return 0;
}

int dijkstra(int from, int to){
    vector<int> distance(N + 1, INF);
    distance[from] = 0;

    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    pq.push(make_pair(from, 0));
    while(!pq.empty()){
        int curDistance = pq.top().second;
        int curNode = pq.top().first;
        pq.pop();

        for(int i = 0; i < route[curNode].size(); i++){
            int nextDistance = curDistance + route[curNode][i].second;
            int nextNode = route[curNode][i].first;

            if(distance[nextNode] > nextDistance){
                distance[nextNode] = nextDistance;
                pq.push(make_pair(nextNode, nextDistance));
            }
        }
    }

    return distance[to];
}
```