[문제 바로가기](https://boj.kr/4299)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int S, D;
    cin >> S >> D;

    if((S + D) % 2 || (S - D) % 2){
        cout << -1 << "\n";
        return 0;
    }

    int team1 = (S + D) / 2;
    int team2 = (S - D) / 2;

    if(team1 < 0 || team2 < 0){
        cout << -1 << "\n";
        return 0;
    }

    cout << max(team1, team2) << " " << min(team1, team2) << "\n";

    return 0;
}
```