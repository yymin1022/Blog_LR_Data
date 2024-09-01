[문제 바로가기](https://boj.kr/1922)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[1001];
vector<pair<int, int>> arr[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int A, B, C;
        cin >> A >> B >> C;

        arr[A].push_back(make_pair(C, B));
        arr[B].push_back(make_pair(C, A));
    }

    priority_queue<pair<int, int>> pq;
    pq.push(make_pair(0, 1));

    int ans = 0;
    while(!pq.empty()){
        int curCost = pq.top().first * -1;
        int curIdx = pq.top().second;
        pq.pop();

        if(isVisit[curIdx]){
            continue;
        }

        ans += curCost;
        isVisit[curIdx] = true;

        for(int i = 0; i < arr[curIdx].size(); i++){
            int nextCost = arr[curIdx][i].first * -1;
            int nextIdx = arr[curIdx][i].second;

            if(!isVisit[nextIdx]){
                pq.push(make_pair(nextCost, nextIdx));
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```