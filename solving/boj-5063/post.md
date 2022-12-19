[문제 바로가기](https://boj.kr/5063)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int r, e, c;
        cin >> r >> e >> c;

        if(r < e - c){
            cout << "advertise" << "\n";
        }else if(r > e- c){
            cout << "do not advertise" << "\n";
        }else{
            cout << "does not matter" << "\n";
        }
    }

    return 0;
}
```