[문제 바로가기](https://boj.kr/11054)

```c++
#include <bits/stdc++.h>

using namespace std;

int A[1001];
int dp1[1001];
int dp2[1001];

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
        dp1[i] = 1;

        for(int j = 0; j < i; j++){
            if(A[j] < A[i] && dp1[j] >= dp1[i]){
                dp1[i] = dp1[j] + 1;
            }
        }
    }

    for(int i = N - 1; i >= 0; i--){
        for(int j = N - 1; j > i; j--){
            if(A[j] < A[i] && dp2[j] >= dp2[i]){
                dp2[i] = dp2[j] + 1;
            }
        }
    }

    int answer = 0;
    for(int i = 0; i < N; i++){
        answer = max(answer, dp1[i] + dp2[i]);
    }

    cout << answer << "\n";

    return 0;
}
```