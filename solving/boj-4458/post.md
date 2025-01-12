[문제 바로가기](https://boj.kr/4458)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cin.ignore();
    while(N--){
        string S;
        getline(cin, S);

        if(S[0] >= 'a'){
            S[0] -= 32;
        }

        cout << S << "\n";
    }

    return 0;
}
```