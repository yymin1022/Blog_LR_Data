[문제 바로가기](https://boj.kr/2358)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<int, int> linesX, linesY;
    for(int i = 0; i < N; i++){
        int X, Y;
        cin >> X >> Y;
        linesX[X]++;
        linesY[Y]++;
    }

    int ans = 0;
    for(auto iter = linesX.begin(); iter != linesX.end(); iter++){
        if(iter->second >= 2){
            ans++;
        }
    }

    for(auto iter = linesY.begin(); iter != linesY.end(); iter++){
        if(iter->second >= 2){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```