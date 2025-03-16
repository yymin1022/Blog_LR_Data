[문제 바로가기](https://boj.kr/5355)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cout << fixed;
    cout.precision(2);

    int T;
    cin >> T;

    while(T--){
        double input;
        cin >> input;

        string S;
        getline(cin, S);

        for(int i = 1; i < S.size(); i += 2){
            if(S[i] == '@'){
                input *= 3;
            }else if(S[i] == '%'){
                input += 5;
            }else{
                input -= 7;
            }
        }

        cout << input << "\n";
    }

    return 0;
}
```