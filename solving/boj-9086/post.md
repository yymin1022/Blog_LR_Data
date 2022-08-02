[문제 바로가기](https://boj.kr/9086)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        string word;
        cin >> word;

        cout << *(word.begin()) << *(word.end() - 1) << "\n";
    }

    return 0;
}```