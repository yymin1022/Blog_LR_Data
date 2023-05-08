[문제 바로가기](https://boj.kr/10942)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool dp[2001][2001];
int arr[2001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> arr[i];
    }

    for(int i = 0; i < N; i++){
        dp[i][i] = true;
        if(i + 1 < N && arr[i] == arr[i + 1]){
            dp[i][i + 1] = true;
        }
    }

    for(int i = N - 2; i >= 0; i--){
        for(int j = i + 2; j < N; j++){
            if(arr[i] == arr[j] && dp[i + 1][j - 1]){
                dp[i][j] = true;
            }
        }
    }

    int M;
    cin >> M;

    for(int i = 0; i < M; i++){
        int S, E;
        cin >> S >> E;

        cout << dp[S - 1][E - 1] << "\n";
    }

    return 0;
}
```