[문제 바로가기](https://boj.kr/5543)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int hamburger = 2000;
    for(int i = 0; i < 3; i++){
        int cost;
        cin >> cost;
        hamburger = min(cost, hamburger);
    }

    int drink = 2000;
    for(int i = 0; i < 2; i++){
        int cost;
        cin >> cost;
        drink = min(cost, drink);
    }

    cout << hamburger + drink - 50 << "\n";

    return 0;
}```