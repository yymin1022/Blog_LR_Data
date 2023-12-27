[문제 바로가기](https://boj.kr/1547)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int M;
    cin >> M;

    int cup[4] = {0, 1, 2, 3};
    for(int i = 0; i < M; i++){
        int X, Y;
        cin >> X >> Y;

        int tmp = cup[X];
        cup[X] = cup[Y];
        cup[Y] = tmp;
    }

    for(int i = 1; i <= 3; i++){
        if(cup[i] == 1){
            cout << i << "\n";
        }
    }

    return 0;
}
```
