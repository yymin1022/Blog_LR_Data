[문제 바로가기](https://boj.kr/1753)

```c++
#include <stdio.h>
#include <iostream>
#include <queue>
#include <vector>

#define INF 999999999

using namespace std;

int v, e, k;
int* distances;

vector<pair<int, int>> graph[1000001];

void dijkstra(int);

int main(void){
    scanf("%d %d", &v, &e);
    scanf("%d", &k);

    k -= 1;
    
    for(int i = 0; i < e; i++){
        int a, b, c;
        scanf("%d %d %d", &a, &b, &c);

        graph[a - 1].push_back({b - 1, c});
    }

    distances = (int*)malloc(sizeof(int) * v);
    
    dijkstra(k);

    for(int i = 0; i < v; i++){
        if(distances[i] == INF){
            printf("INF\n");
        }else{
            printf("%d\n", distances[i]);
        }
    }
}

void dijkstra(int start){
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    
    fill(distances, distances + v, INF);
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
}```