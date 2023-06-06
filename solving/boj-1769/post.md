[문제 바로가기](https://boj.kr/1769)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string X;
    cin >> X;

    int cnt = 0;
    while(X.size() > 1){
        int tmp = 0;
        for(int i = 0; i < X.size(); i++){
            tmp += X[i] - '0';
        }
        X = to_string(tmp);
        cnt++;
    }

    cout << cnt << "\n";
    if(stoi(X) % 3){
        cout << "NO" << "\n";
    }else{
        cout << "YES" << "\n";
    }

    return 0;
}
```