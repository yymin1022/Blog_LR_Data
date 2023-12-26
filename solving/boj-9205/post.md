[문제 바로가기](https://boj.kr/9205)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        pair<int, int> home, festival;
        cin >> N >> home.first >> home.second;

        vector<pair<int, int>> store;
        vector<bool> isVisit;
        for(int i = 0; i < N; i++){
            int x, y;
            cin >> x >> y;
            isVisit.push_back(false);
            store.push_back(make_pair(x, y));
        }

        cin >> festival.first >> festival.second;

        queue<pair<int, int>> bfsQ;
        bfsQ.push(home);
        bool isHappy = false;
        while(!bfsQ.empty()){
            int curX = bfsQ.front().first;
            int curY = bfsQ.front().second;
            bfsQ.pop();

            for(int i = 0; i < N; i++){
                if(abs(store[i].first - curX) + abs(store[i].second - curY) <= 1000){
                    if(!isVisit[i]){
                        bfsQ.push(store[i]);
                        isVisit[i] = true;
                    }
                }
            }

            if(abs(festival.first - curX) + abs(festival.second - curY) <= 1000){
                isHappy = true;
                break;
            }
        }

        cout << (isHappy ? "happy" : "sad") << "\n";
    }

    return 0;
}
```