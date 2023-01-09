[문제 바로가기](https://boj.kr/14732)

```c++
#include <bits/stdc++.h>

using namespace std;

bool party[501][501];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 0; i < N; i++){
        int x1, x2, y1, y2;
        cin >> x1 >> y1 >> x2 >> y2;

        for(int j = x1; j < x2; j++){
            for(int k = y1; k < y2; k++){
                if(!party[j][k]){
                    ans++;
                    party[j][k] = true;
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```