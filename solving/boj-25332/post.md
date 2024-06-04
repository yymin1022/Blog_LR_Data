[문제 바로가기](https://boj.kr/25332)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> A;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        A.push_back(input);
    }

    vector<long long> B;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        A[i] -= input;
    }

    long long ans = 0;
    long long sum = 0;
    map<long long, int> cnt;
    cnt[0] = 1;
    for (int i = 0; i < N; i++) {
        sum += A[i];
        ans += cnt[sum];
        cnt[sum]++;
    }

    cout << ans << "\n";

    return 0;
}
```