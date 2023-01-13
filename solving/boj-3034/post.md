[문제 바로가기](https://boj.kr/3034)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, H, W;
    cin >> N >> H >> W;

    int ans = 0;
    for(int i = 0; i < N; i++) {
        int len;
        cin >> len;

        if (H * H + W * W >= len * len) {
            cout << "DA" << "\n";
        }else{
            cout << "NE" << "\n";
        }
    }

    return 0;
}
```