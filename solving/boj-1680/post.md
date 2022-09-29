[문제 바로가기](https://boj.kr/1680)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int W, N;
        cin >> W >> N;

        vector<pair<int, int>> trash;
        for(int i = 0; i < N; i++){
            int dist, trashW;
            cin >> dist >> trashW;
            trash.push_back(make_pair(dist, trashW));
        }

        int cur = 0;
        int dist = 0;
        int prev = 0;
        for(int i = 0; i < N; i++){
            dist += trash[i].first - prev;
            prev = trash[i].first;

            if(cur + trash[i].second < W){
                cur += trash[i].second;
            }else if(cur + trash[i].second == W){
                cur = 0;
                if(i < N - 1){
                    dist += trash[i].first * 2;
                }
            }else{
                cur = trash[i].second;
                dist += trash[i].first * 2;
            }

            if(i == N - 1){
                dist += trash[i].first;
            }
        }

        cout << dist << "\n";
    }

    return 0;
}
```