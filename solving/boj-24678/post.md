[문제 바로가기](https://boj.kr/24678)

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
        int x, y, z;
        cin >> x >> y >> z;

        int cnt = 0;
        if(x % 2){
            cnt++;
        }
        if(y % 2){
            cnt++;
        }
        if(z % 2){
            cnt++;
        }

        if(cnt == 3 || cnt == 2){
            cout << "B" << "\n";
        }else{
            cout << "R" << "\n";
        }
    }

    return 0;
}
```