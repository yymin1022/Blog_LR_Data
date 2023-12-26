[문제 바로가기](https://boj.kr/11059)

```c++
#include <bits/stdc++.h>

using namespace std;

int sum[1001][1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    for(int i = 0; i < S.size(); i++){
        sum[i][i] = S[i] - '0';

        for(int j = i + 1; j < S.size(); j++){
            sum[i][j] = sum[i][j - 1] + S[j] - '0';
        }
    }

    int ans = 0;
    for(int i = 0; i < S.size(); i++){
        int idx = i;
        for(int j = i + 1; j < S.size(); j += 2){
            if(sum[i][j] % 2 == 0 && sum[i][j] / 2 == sum[i][idx]){
                ans = max(j - i + 1, ans);
            }
            idx++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```