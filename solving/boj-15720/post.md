[문제 바로가기](https://boj.kr/15720)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int B, C, D;
    cin >> B >> C >> D;

    int setCnt = min(min(B, C), D);
    int sum = 0;

    vector<int> burger;
    for(int i = 0; i < B; i++){
        int input;
        cin >> input;
        burger.push_back(input);
        sum += input;
    }

    vector<int> side;
    for(int i = 0; i < C; i++){
        int input;
        cin >> input;
        side.push_back(input);
        sum += input;
    }

    vector<int> drink;
    for(int i = 0; i < D; i++){
        int input;
        cin >> input;
        drink.push_back(input);
        sum += input;
    }

    cout << sum << "\n";

    sort(burger.begin(), burger.end(), greater<int>());
    sort(drink.begin(), drink.end(), greater<int>());
    sort(side.begin(), side.end(), greater<int>());

    sum = 0;
    for(int i = 0; i < setCnt; i++){
        sum += burger[i];
        sum += drink[i];
        sum += side[i];
    }

    sum *= 0.9;

    for(int i = setCnt; i < B; i++){
        sum += burger[i];
    }

    for(int i = setCnt; i < C; i++){
        sum += side[i];
    }

    for(int i = setCnt; i < D; i++){
        sum += drink[i];
    }

    cout << sum << "\n";

    return 0;
}
```