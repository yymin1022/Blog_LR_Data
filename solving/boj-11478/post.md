[문제 바로가기](https://boj.kr/11478)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    set<string> words;
    string temp = "";
    for(int i = 0; i < S.size(); i++){
        temp = "";

        for(int j = i; j < S.size(); j++){
            temp += S[j];
            words.insert(temp);
        }
    }

    cout << words.size() << "\n";

    return 0;
}```