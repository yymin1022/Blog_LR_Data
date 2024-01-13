[문제 바로가기](https://boj.kr/21964)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    for(int i = S.size() - 5; i < S.size(); i++){
        cout << S[i];
    }
    cout << "\n";

    return 0;
}
```