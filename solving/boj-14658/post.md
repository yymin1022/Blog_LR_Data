[문제 바로가기](https://boj.kr/14658)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M, L, K;
vector<pair<int, int>> star;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> M >> L >> K;

    for(int i = 0; i < K; i++){
        int x, y;
        cin >> x >> y;
        star.push_back(make_pair(x, y));
    }

    int ans = 0;
    for(int i = 0; i < K; i++){
        for(int j = 0; j < K; j++){
            int tmp = 0;
            for(int k = 0; k < K; k++){
                if(star[i].first <= star[k].first && star[k].first <= star[i].first + L && star[j].second <= star[k].second && star[k].second <= star[j].second + L){
                    tmp++;
                }
            }

            ans = max(tmp, ans);
        }
    }

    cout << K - ans << "\n";

    return 0;
}
```