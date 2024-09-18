[문제 바로가기](https://boj.kr/12354)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int N;
        cin >> N;

        vector<int> height;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            height.push_back(input);
        }

        int ans = 0;
        for(int i = 1; i < N; i++){
            if(height[i - 1] >= height[i]){
                ans++;
            }
        }

        cout << "Case #" << t << ": ";
        cout << ans << "\n";
    }

    return 0;
}
```
