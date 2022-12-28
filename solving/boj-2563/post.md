[문제 바로가기](https://boj.kr/2563)

```c++
#include <bits/stdc++.h>

using namespace std;

int paper[101][101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    int ans = 0;
    for(int i = 0; i < N; i++){
        int X, Y;
        cin >> X >> Y;

        for(int j = X; j < X + 10; j++){
            for(int k = Y; k < Y + 10; k++){
                if(!paper[j][k]){
                    ans++;
                    paper[j][k] = 1;
                }
            }
        }
    }

    cout << ans << "\n";
    
    return 0;
}
```