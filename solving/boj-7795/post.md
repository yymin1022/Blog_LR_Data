[문제 바로가기](https://boj.kr/7795)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, M;
        cin >> N >> M;

        vector<int> A(N);
        for(int i = 0; i < N; i++){
            cin >> A[i];
        }

        vector<int> B(M);
        for(int i = 0; i < M; i++){
            cin >> B[i];
        }

        sort(A.begin(), A.end());
        sort(B.begin(), B.end());

        int cnt = 0;
        for(int i = 0; i < N; i++){
            cnt += lower_bound(B.begin(), B.end(), A[i]) - B.begin();
        }

        cout << cnt << "\n";
    }

    return 0;
}```