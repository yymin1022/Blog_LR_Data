[문제 바로가기](https://boj.kr/1094)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int X;
    cin >> X;

    int ans = 0;
    while(X > 0){
        if(X % 2 == 1){
            ans++;
        }

        X /= 2;
    }

    cout << ans << "\n";

    return 0;
}

```