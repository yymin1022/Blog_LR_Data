[문제 바로가기](https://boj.kr/20114)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, H, W;
    cin >> N >> H >> W;

    string ans;
    for(int i = 0; i < N; i++){
        ans.push_back('?');
    }
    for(int i = 0; i < H; i++){
        string input;
        cin >> input;

        for(int j = 0; j < N * W; j++){
            if(input[j] != '?'){
                ans[j / W] = input[j];
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```
