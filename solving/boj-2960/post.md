[문제 바로가기](https://boj.kr/2960)

```c++
#include <bits/stdc++.h>

using namespace std;

bool dp[1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 2; i <= N; i++){
        for(int j = i; j <= N; j += i){
            if(!dp[j]){
                dp[j] = true;
                K--;

                if(!K){
                    cout << j << "\n";
                    return 0;
                }
            }
        }
    }

    return 0;
}

```