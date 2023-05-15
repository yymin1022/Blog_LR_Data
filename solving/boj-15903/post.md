[문제 바로가기](https://boj.kr/15903)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    priority_queue<long long, vector<long long>, greater<long long>> card;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        card.push(input);
    }

    for(int i = 0; i < M; i++){
        long long X = card.top();
        card.pop();
        long long Y = card.top();
        card.pop();

        card.push(X + Y);
        card.push(X + Y);
    }

    long long ans = 0;
    while(!card.empty()){
        ans += card.top();
        card.pop();
    }

    cout << ans << "\n";

    return 0;
}
```