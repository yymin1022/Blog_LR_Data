[문제 바로가기](https://boj.kr/27964)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    set<string> cheese;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        if(input.size() >= 6 && input.substr(input.size() - 6, 6) == "Cheese"){
            cheese.insert(input);
        }
    }

    cout << (cheese.size() > 3 ? "yummy" : "sad") << "\n";

    return 0;
}
```