[문제 바로가기](https://boj.kr/14471)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> A;
    for(int i = 0; i < M; i++){
        int a, b;
        cin >> a >> b;
        A.push_back(a);
    }

    sort(A.begin(), A.end(), greater<int>());

    int ans = 0;
    int cnt = 0;
    for(int i = 0; i < M; i++){
        cnt++;
        if(A[i] < N){
            ans += N - A[i];
        }

        if(cnt == M - 1){
            break;
        }
    }

    cout << ans << "\n";

    return 0;
}
```