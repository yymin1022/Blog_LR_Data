[문제 바로가기](https://boj.kr/2143)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long T, N, M;
    cin >> T >> N;

    vector<long long> A;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        A.push_back(input);
    }

    cin >> M;

    vector<long long> B;
    for(int i = 0; i < M; i++){
        long long input;
        cin >> input;
        B.push_back(input);
    }

    for(int i = 0; i < N; i++){
        long long sum = A[i];
        for(int j = i + 1; j < N; j++){
            sum += A[j];
            A.push_back(sum);
        }
    }

    for(int i = 0; i < M; i++){
        long long sum = B[i];
        for(int j = i + 1; j < M; j++){
            sum += B[j];
            B.push_back(sum);
        }
    }

    sort(B.begin(), B.end());

    long long ans = 0;
    for(int i = 0; i < A.size(); i++){
        int from = lower_bound(B.begin(), B.end(), T - A[i]) - B.begin();
        int to = upper_bound(B.begin(), B.end(), T - A[i]) - B.begin();
        ans += to - from;
    }

    cout << ans << "\n";

    return 0;
}
```