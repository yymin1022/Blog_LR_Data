[문제 바로가기](https://boj.kr/22351)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int startNum = 0;
    for(int i = 0; i < 3; i++){
        startNum = startNum * 10 + (S[i] - '0');

        string tmp = "";
        for(int j = startNum; tmp.size() <= S.size(); j++){
            tmp += to_string(j);

            if(tmp == S){
                cout << startNum << " ";
                cout << j << "\n";
                return 0;
            }
        }
    }

    return 0;
}

```