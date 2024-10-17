[문제 바로가기](https://boj.kr/17396)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisible[100001];
long long dist[100001];
vector<pair<long long, int>> arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        dist[i] = 987654321000000000;
        isVisible[i] = (input != 0);
    }

    for(int i = 0; i < M; i++){
        int A, B, T;
        cin >> A >> B >> T;

        if((!isVisible[A] && !isVisible[B]) || A == N - 1 || B == N - 1){
            arr[A].push_back(make_pair(T, B));
            arr[B].push_back(make_pair(T, A));
        }
    }

    priority_queue<pair<long long, int>, vector<pair<long long, int>>, greater<pair<long long, int>>> pq;
    pq.push(make_pair(0, 0));
    dist[0] = 0;
    while(!pq.empty()){
        long long curDist = pq.top().first;
        int curNode = pq.top().second;
        pq.pop();

        if(curNode == N - 1){
            cout << dist[curNode] << "\n";
            return 0;
        }

        if(curDist > dist[curNode]){
            continue;
        }

        for(int i = 0; i < arr[curNode].size(); i++){
            long long newDist = curDist + arr[curNode][i].first;
            int newNode = arr[curNode][i].second;

            if(dist[newNode] > newDist){
                dist[newNode] = newDist;
                pq.push(make_pair(newDist, newNode));
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}
```