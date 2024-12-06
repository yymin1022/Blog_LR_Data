[문제 바로가기](https://boj.kr/4872)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int ans[10] = {0, 0, 0, 0};

    string S;
    while(cin >> S){
        for(int i = 0; i < S.size(); i++){
            ans[i] += S[i] - '0';
            ans[i] %= 10;
        }
    }

    for(int i = 0; i < S.size(); i++){
        cout << ans[i];
    }

    return 0;
}

```