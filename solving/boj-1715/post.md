[문제 바로가기](https://boj.kr/1715)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N == 1){
        cout << 0 << "\n";
        return 0;
    }

    priority_queue<long long, vector<long long>, greater<long long>> card;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        card.push(input);
    }

    long long ans = 0;
    while(!card.empty()){
        long long card1 = card.top();
        card.pop();
        long long card2 = card.top();
        card.pop();

        long long cardSum = card1 + card2;
        ans += cardSum;

        if(!card.empty()){
            card.push(cardSum);
        }
    }

    cout << ans << "\n";

    return 0;
}
```