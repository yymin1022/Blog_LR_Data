[문제 바로가기](https://boj.kr/5568)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isUsed[10];
int N, K;
set<string> res;
vector<string> card;
vector<string> tmp;

void dfs(int cnt){
    if(cnt == K){
        string make;
        for(int i = 0; i < tmp.size(); i++){
            make += tmp[i];
        }
        res.insert(make);
    }

    for(int i = 0; i < N; i++){
        if(isUsed[i]){
            continue;
        }

        isUsed[i] = true;
        tmp.push_back(card[i]);
        dfs(cnt + 1);
        isUsed[i] = false;
        tmp.pop_back();
    }
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> K;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        card.push_back(input);
    }

    dfs(0);

    cout << res.size() << "\n";

    return 0;
}
```