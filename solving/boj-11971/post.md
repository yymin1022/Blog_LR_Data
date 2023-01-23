[문제 바로가기](https://boj.kr/11971)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> limit(1);
    int tmp = 1;
    for(int i = 0; i < N; i++){
        int len, spd;
        cin >> len >> spd;
        for(int j = 0; j < len; j++){
            limit.push_back(spd);
        }
    }

    int ans = 0;
    int cur = 0;
    tmp = 1;
    for(int i = 0; i < M; i++){
        int len, spd;
        cin >> len >> spd;
        cur += len;
        while(tmp <= cur){
            ans = max(spd - limit[tmp], ans);
            tmp++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```