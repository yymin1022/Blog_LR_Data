[문제 바로가기](https://boj.kr/24396)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[300001];
int dist[300001];
vector<int> arr[300001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, E;
    cin >> N >> E;

    for(int i = 0; i < E; i++){
        int X, Y;
        cin >> X >> Y;
        arr[X].emplace_back(Y);
        arr[Y].emplace_back(X);
    }

    int curDist = 2;
    dist[1] = 1;

    queue<int> bfsQ;
    bfsQ.push(1);
    while(!bfsQ.empty()){
        int size = bfsQ.size();

        memset(cnt, 0, sizeof(cnt));
        while(!bfsQ.empty()){
            int cur = bfsQ.front();
            bfsQ.pop();

            for(int i = 0; i < arr[cur].size(); i++){
                cnt[arr[cur][i]]++;
            }
        }

        for(int i = 1; i <= N; i++){
            if(dist[i] == 0 && cnt[i] < size){
                dist[i] = curDist;
                bfsQ.push(i);
            }
        }

        curDist++;
    }

    for(int i = 1; i <= N; i++){
        cout << dist[i] - 1 << "\n";
    }

    return 0;
}
```