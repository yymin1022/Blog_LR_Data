[문제 바로가기](https://boj.kr/1911)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<pair<int, int>> pool;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;

        pool.push_back(make_pair(A, B));
    }

    sort(pool.begin(), pool.end());

    int ans = 0;
    int cur = 0;

    for(int i = 0; i < N; i++){
        if(pool[i].first <= cur && cur < pool[i].second){
            int X = (pool[i].second - cur) / L;
            int Y = (pool[i].second - cur) % L;

            ans += X;
            cur += X * L;

            if(Y != 0){
                ans++;
                cur += L;
            }
        }else if(cur < pool[i].first){
            cur = pool[i].first;
            i--;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
