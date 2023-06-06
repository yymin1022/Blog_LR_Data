[문제 바로가기](https://boj.kr/1197)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[10001];

struct Item{
    int edge;
    int cost;

    bool operator<(Item A) const{
        return cost > A.cost;
    }
};

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int V, E;
    cin >> V >> E;

    vector<Item> arr[10001];
    for(int i = 0; i < E; i++){
        int A, B, C;
        cin >> A >> B >> C;
        arr[A].push_back({B, C});
        arr[B].push_back({A, C});
    }

    priority_queue<Item> pq;
    pq.push({1, 0});

    int ans = 0;
    while(!pq.empty()){
        int edge = pq.top().edge;
        int cost = pq.top().cost;
        pq.pop();

        if(isVisit[edge]){
            continue;
        }

        ans += cost;
        isVisit[edge] = true;

        for(int i = 0; i < arr[edge].size(); i++){
            pq.push(arr[edge][i]);
        }
    }

    cout << ans << "\n";

    return 0;
}
```