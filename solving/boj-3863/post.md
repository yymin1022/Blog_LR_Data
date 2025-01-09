[문제 바로가기](https://boj.kr/3863)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int N, M;
        cin >> N >> M;

        if(N == 0 && M == 0){
            break;
        }

        vector<pair<long long, long long>> call;
        for(int i = 0; i < N; i++){
            long long src, dest, start, dur;
            cin >> src >> dest >> start >> dur;
            call.push_back(make_pair(start, start + dur));
        }

        for(int i = 0; i < M; i++){
            long long start, dur;
            cin >> start >> dur;

            int cnt = 0;
            for(int j = 0; j < N; j++){
                if(min(start + dur, call[j].second) - max(start, call[j].first) > 0){
                    cnt++;
                }
            }

            cout << cnt << "\n";
        }
    }

    return 0;
}
```