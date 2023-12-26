[문제 바로가기](https://boj.kr/16208)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long sum = 0;
    vector<int> stick;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        stick.push_back(input);
        sum += input;
    }

    long long ans = 0;
    for(int i = 0; i < N; i++){
        ans += stick[i] * (sum - stick[i]);
    }

    cout << ans / 2 << "\n";

    return 0;
}
```
