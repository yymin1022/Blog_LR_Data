[문제 바로가기](https://boj.kr/18221)

```c++
#include <bits/stdc++.h>

using namespace std;

int desk[1001][1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int sR, sC, pR, pC;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> desk[i][j];

            if(desk[i][j] == 2){
                sR = i;
                sC = j;
            }else if(desk[i][j] == 5){
                pR = i;
                pC = j;
            }
        }
    }

    int cnt = 0;
    for(int i = (sR > pR ? pR : sR); i <= (sR > pR ? sR : pR); i++){
        for(int j = (sC > pC ? pC : sC); j <= (sC > pC ? sC : pC); j++){
            if(desk[i][j] == 1){
                cnt++;
            }
        }
    }

    if(sqrt((sR - pR) * (sR - pR) + (sC - pC) * (sC - pC)) >= 5 && cnt >= 3){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```