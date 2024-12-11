[문제 바로가기](https://boj.kr/25045)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<long long> A;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        A.push_back(input);
    }

    vector<long long> B;
    for(int i = 0; i < M; i++){
        long long input;
        cin >> input;
        B.push_back(input);
    }

    sort(A.begin(), A.end(), greater<>());
    sort(B.begin(), B.end());

    long long ans = 0;
    for(int i = 0; i < min(N, M); i++){
        if(A[i] - B[i] > 0){
            ans += A[i] - B[i];
        }
    }

    cout << ans << "\n";

    return 0;
}
```