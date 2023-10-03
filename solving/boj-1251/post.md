[문제 바로가기](https://boj.kr/1251)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    vector<string> result;
    for(int i = 1; i < S.size() - 1; i++){
        for(int j = i + 1; j < S.size(); j++){
            string res;
            string tmp = S.substr(0, i);
            reverse(tmp.begin(), tmp.end());
            res += tmp;
            tmp = S.substr(i, j - i);
            reverse(tmp.begin(), tmp.end());
            res += tmp;
            tmp = S.substr(j, S.size());
            reverse(tmp.begin(), tmp.end());
            res += tmp;

            result.push_back(res);
        }
    }

    sort(result.begin(), result.end());

    cout << result[0] << "\n";

    return 0;
}
```