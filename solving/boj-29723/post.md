[문제 바로가기](https://boj.kr/29723)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    map<string, int> score;
    for(int i = 0; i < N; i++){
        string name;
        int input;
        cin >> name >> input;
        score[name] = input;
    }

    int ans = 0;
    for(int i = 0; i < K; i++){
        string name;
        cin >> name;
        ans += score[name];
        score[name] = -1;
    }

    vector<int> tmp;
    for(auto iter = score.begin(); iter != score.end(); iter++){
        if(iter->second >= 0) {
            tmp.push_back(iter->second);
        }
    }

    sort(tmp.begin(), tmp.end());

    int worst = ans;
    for(int i = 0; i < M - K; i++){
        worst += tmp[i];
    }

    int best = ans;
    for(int i = 0; i < M - K; i++){
        best += tmp[tmp.size() - i - 1];
    }

    cout << worst << " ";
    cout << best << "\n";

    return 0;
}
```
