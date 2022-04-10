[문제 바로가기](https://boj.kr/2775)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    int map[15][15];

    for(int i = 0; i < 15; i++){
        for(int j = 1; j < 15; j++){
            if(i == 0){
                map[i][j] = j;
                continue;
            }
            if(j == 1){
                map[i][j] = map[i - 1][j];
                continue;
            }
            map[i][j] = map[i][j - 1] + map[i - 1][j];
        }
    }

    for(int i = 0; i < T; i++){
        int k, n;
        cin >> k >> n;

        cout << map[k][n] << "\n";
    }

    return 0;
}
```