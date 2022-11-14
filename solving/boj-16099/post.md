[문제 바로가기](https://boj.kr/16099)

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
        long long lt, wt, le, we;
        cin >> lt >> wt >> le >> we;

        long long valT = lt * wt;
        long long valE = le * we;

        if(valT > valE){
            cout << "TelecomParisTech" << "\n";
        }else if(valT < valE){
            cout << "Eurecom" << "\n";
        }else{
            cout << "Tie" << "\n";
        }
    }

    return 0;
}
```