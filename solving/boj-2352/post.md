[문제 바로가기](https://boj.kr/2352)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> dp;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(dp.empty() || input > dp.back()){
            dp.push_back(input);
        }else{
            int idx = lower_bound(dp.begin(), dp.end(), input) - dp.begin();
            dp[idx] = input;
        }
    }

    cout << dp.size() << "\n";

    return 0;
}
```