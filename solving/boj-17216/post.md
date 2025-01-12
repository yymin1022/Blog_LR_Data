[문제 바로가기](https://boj.kr/17216)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
        dp[i] = input;
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < i; j++){
            if(arr[j] > arr[i]){
                dp[i] = max(dp[j] + arr[i], dp[i]);
            }
        }
        ans = max(dp[i], ans);
    }

    cout << ans << "\n";

    return 0;
}

```