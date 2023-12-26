[문제 바로가기](https://boj.kr/10214)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        pair<int, int> score = make_pair(0, 0);
        for(int i = 0; i < 9; i++){
            int Y, K;
            cin >> Y >> K;
            score.first += Y;
            score.second += K;
        }

        cout << (score.first > score.second ? "Yonsei" : score.first < score.second ? "Korea" : "Draw") << "\n";
    }

    return 0;
}
```