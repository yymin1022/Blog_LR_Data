[문제 바로가기](https://boj.kr/14493)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> bot;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        bot.push_back(make_pair(A + B, B));
    }

    int cur = 0;
    int time = 0;
    while(cur < N){
        if(time % bot[cur].first >= bot[cur].second){
            cur++;
        }
        time++;
    }

    cout << time << "\n";

    return 0;
}
```