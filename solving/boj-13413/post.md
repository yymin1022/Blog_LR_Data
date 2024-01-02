[문제 바로가기](https://boj.kr/1236)

```c++
#include <bits/stdc++.h>

using namespace std;

 char table[51][51];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    map<int, int> cntX;
    map<int, int> cntY;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            char input;
            cin >> input;
            if(input == 'X'){
                cntX[i]++;
                cntY[j]++;
            }
        }
    }

    int cntI = 0;
    int cntJ = 0;
    for(int i = 0; i < N; i++){
        if(cntX[i] == 0){
            cntI++;
        }
    }

    for(int i = 0; i < M; i++){
        if(cntY[i] == 0){
            cntJ++;
        }
    }

    cout << ((cntI > cntJ) ? cntI : cntJ) << "\n";
    
    return 0;
}
```