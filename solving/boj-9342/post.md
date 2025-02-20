[문제 바로가기](https://boj.kr/9342)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    regex reg(R"(^[A-F]?A+F+C+[A-F]?$)");

    int T;
    cin >> T;

    while(T--){
        string S;
        cin >> S;

        cout << (regex_match(S, reg) ? "Infected!" : "Good") << "\n";
    }

    return 0;
}
```