[문제 바로가기](https://boj.kr/28432)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int idx;
    vector<string> words;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        if(input == "?"){
            idx = i;
        }
        words.push_back(input);
    }

    int M;
    cin >> M;

    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        if(count(words.begin(), words.end(), input) > 0)
            continue;
        if(idx > 0 && words[idx - 1].back() != input.front())
            continue;
        if(idx < N - 1 && words[idx + 1].front() != input.back())
            continue;
        cout << input << "\n";
        return 0;
    }

    return 0;
}
```
