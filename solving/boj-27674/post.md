[문제 바로가기](https://boj.kr/27674)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        string input;
        cin >> input;

        sort(input.begin(), input.end(), greater<char>());

        int tmp = input[input.size() - 1] - '0';

        long long result = stoll(input.substr(0, input.size() - 1));
        cout << result + tmp << "\n";
    }

    return 0;
}
```