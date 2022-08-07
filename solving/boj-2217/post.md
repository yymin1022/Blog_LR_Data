[문제 바로가기](https://boj.kr/2217)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    vector<long long> rope;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        rope.push_back(input);
    }

    sort(rope.begin(), rope.end());

    long long ans = 0;
    for(int i = N - 1; i >= 0; i--){
        long long sum = rope[i] * (N - i);

        ans = max(sum, ans);
    }

    cout << ans << "\n";

    return 0;
}
```