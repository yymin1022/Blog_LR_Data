[문제 바로가기](https://boj.kr/18126)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dist[5001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, long long>> arr[5001];
    for(int i = 0; i < N - 1; i++){
        long long A, B, C;
        cin >> A >> B >> C;

        arr[A].push_back(make_pair(B, C));
        arr[B].push_back(make_pair(A, C));
    }

    for(int i = 0; i < 5001; i++){
        dist[i] = 5e12+1;
    }

    queue<pair<int, long long>> bfsQ;
    bfsQ.push(make_pair(1, 0));
    dist[1] = 0;

    long long ans = 0;
    while(!bfsQ.empty()){
        long long curC = bfsQ.front().second;
        int curX = bfsQ.front().first;
        bfsQ.pop();

        for(int i = 0; i < arr[curX].size(); i++){
            long long nextC = arr[curX][i].second;
            int nextX = arr[curX][i].first;

            if(dist[nextX] > curC + nextC){
                bfsQ.push(make_pair(nextX, curC + nextC));
                dist[nextX] = curC + nextC;
                ans = max(dist[nextX], ans);
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```