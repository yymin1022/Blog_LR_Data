[문제 바로가기](https://boj.kr/11053)

```c++
#include <bits/stdc++.h>

using namespace std;

int A[1001];
int dp[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> A[i];
    }

    for(int i = 0; i < N; i++){
        dp[i] = 1;

        for(int j = 0; j < i; j++){
            if(A[j] < A[i] && dp[j] >= dp[i]){
                dp[i] = dp[j] + 1;
            }
        }
    }

    int answer = 0;
    for(int i = 0; i < N; i++){
        answer = max(answer, dp[i]);
    }

    cout << answer << "\n";

    return 0;
}
```