[문제 바로가기](https://boj.kr/19944)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, M;
    cin >> N >> M;

    if(M <= 2){
        cout << "NEWBIE!" << "\n";
    }else if(M <= N){
        cout << "OLDBIE!" << "\n";
    }else{
        cout << "TLE!" << "\n";
    }

    return 0;
}
```