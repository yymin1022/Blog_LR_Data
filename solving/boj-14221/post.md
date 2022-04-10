[문제 바로가기](https://boj.kr/14221)

```c++
#include <stdio.h>
#include <iostream>
#include <queue>
#include <vector>

#define INF 999999999

using namespace std;

int n, m, start;
int* distances;

vector<pair<int, int>> graph[1000001];

void dijkstra(int);

int main(void){
    scanf("%d %d", &n, &m);
    
    for(int i = 0; i < m; i++){
        int a, b, c;
        scanf("%d %d %d", &a, &b, &c);

        graph[a - 1].push_back({b - 1, c});
        graph[b - 1].push_back({a - 1, c});
    }

    distances = (int*)malloc(sizeof(int) * n);
    
    int p, q;
    scanf("%d %d", &p, &q);

    int* homes = (int*)malloc(sizeof(int) * p);
    int* stores = (int*)malloc(sizeof(int) * q);

    for(int i = 0; i < p; i++){
        scanf("%d", homes + i);
        *(homes + i) -= 1;
    }
    for(int i = 0; i < q; i++){
        scanf("%d", stores + i);
        *(stores + i) -= 1;
    }

    pair<int, int> result = {INF, INF};

    for(int i = 0; i < p; i++){
        dijkstra(homes[i]);

        for(int j = 0; j < q; j++){
            if(distances[stores[j]] > result.first) continue;
            if(distances[stores[j]] == result.first){
                if(result.second > homes[i]){
                    result = {distances[stores[j]], homes[i]};
                }
                continue;
            }
            result = {distances[stores[j]], homes[i]};
        }
    }

    printf("%d\n", result.second + 1);
}

void dijkstra(int start){
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    
    fill(distances, distances + n, INF);
    pq.push({distances[start]=0, start});

        while(!pq.empty()){
            auto now = pq.top();
            pq.pop();

            if(now.first > distances[now.second]) continue;
            for(int i =0; i < graph[now.second].size(); i++){
                int nextDist = now.first + graph[now.second][i].second;
                if(nextDist < distances[graph[now.second][i].first])
                    pq.push({distances[graph[now.second][i].first] = nextDist, graph[now.second][i].first});
            }
        }
}
```