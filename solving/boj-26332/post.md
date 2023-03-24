[문제 바로가기](https://boj.kr/26332)

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
        int C, P;
        cin >> C >> P;

        cout << C << " " << P << "\n";

        if(C == 1){
            cout << P << "\n";
        }else{
            cout << C * P - (C - 1) * 2 << "\n";
        }
    }

    return 0;
}
```