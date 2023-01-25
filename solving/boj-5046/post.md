[문제 바로가기](https://boj.kr/5046)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, B, H, W;
    cin >> N >> B >> H >> W;

    bool isAble = false;
    int ans = B;
    for(int i = 0; i < H; i++){
        int P;
        cin >> P;

        for(int j = 0; j < W; j++){
            int A;
            cin >> A;

            if(A >= N){
                int tmp = P * N;
                if(tmp <= B){
                    ans = min(tmp, ans);
                    isAble = true;
                }
            }
        }
    }

    if(isAble) {
        cout << ans << "\n";
    }else{
        cout << "stay home" << "\n";
    }

    return 0;
}
```