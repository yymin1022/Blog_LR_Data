[문제 바로가기](https://boj.kr/20362)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    int ansIdx = 0;
    vector<pair<string, string>> chat;
    for(int i = 0; i < N; i++){
        string nick, word;
        cin >> nick >> word;
        chat.push_back(make_pair(nick, word));

        if(nick == S){
            ansIdx = i;
        }
    }

    int ans = 0;
    for(int i = 0; i < ansIdx; i++){
        if(chat[i].second == chat[ansIdx].second){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```