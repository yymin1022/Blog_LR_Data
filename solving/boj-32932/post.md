[문제 바로가기](https://boj.kr/32932)

```c++
#include <bits/stdc++.h>

using namespace std;

bool arr[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < N; i++){
        int x, y;
        cin >> x >> y;
        arr[x + 500][y + 500] = true;
    }

    string cmd;
    cin >> cmd;

    int ansX = 0;
    int ansY = 0;
    for(int i = 0; i < K; i++){
        if(cmd[i] == 'L'){
            if(ansX - 1 >= -500 && !arr[ansX - 1 + 500][ansY + 500]){
                ansX--;
            }
        }else if(cmd[i] == 'U'){
            if(ansY + 1 <= 500 && !arr[ansX + 500][ansY + 1 + 500]){
                ansY++;
            }
        }else if(cmd[i] == 'R'){
            if(ansX + 1 <= 500 && !arr[ansX + 1 + 500][ansY + 500]){
                ansX++;
            }
        }else{
            if(ansY - 1 >= -500 && !arr[ansX + 500][ansY - 1 + 500]){
                ansY--;
            }
        }
    }

    cout << ansX << " ";
    cout << ansY << "\n";

    return 0;
}
```
