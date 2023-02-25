[문제 바로가기](https://boj.kr/14221)

```c++
#include <bits/stdc++.h>

using namespace std;

int dijkstra(int);

bool store[5001];
int dist[5001];
int N, M, p, q;
vector<pair<int, int>> cost[5001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i <= N; i++){
        dist[i] = 2147483647;
    }

    for(int i = 0; i < M; i++){
        int a, b, c;
        cin >> a >> b >> c;
        cost[a].push_back(make_pair(b, c));
        cost[b].push_back(make_pair(a, c));
    }

    cin >> p >> q;

    vector<int> home;
    for(int i = 0; i < p; i++){
        int input;
        cin >> input;
        home.push_back(input);
    }

    sort(home.begin(), home.end());

    for(int i = 0; i < q; i++){
        int input;
        cin >> input;
        store[input] = true;
    }

    int minDist = 2147483647;
    int minHome = -1;
    for(int i = 0; i < p; i++){
        int tmp = dijkstra(home[i]);
        if(tmp < minDist){
            minDist = tmp;
            minHome = home[i];
        }
    }

    cout << minHome << "\n";

    return 0;
}

int dijkstra(int from){
    dist[from] = 0;
    priority_queue<pair<int, int>> pq;
    pq.push(make_pair(from, 0));

    int minDist = 2147483647;
    while(!pq.empty()){
        int cur = pq.top().first;
        int curDist = -pq.top().second;
        pq.pop();

        if(store[cur]){
            minDist = min(curDist, minDist);
        }

        if(dist[cur] < curDist){
            continue;
        }

        for(int i = 0; i < cost[cur].size(); i++){
            int next = cost[cur][i].first;
            int nextDist = curDist + cost[cur][i].second;

            if(nextDist < dist[next]){
                dist[next] = nextDist;
                pq.push(make_pair(next, -nextDist));
            }
        }
    }

    return minDist;
}
```