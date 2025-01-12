[문제 바로가기](https://boj.kr/22971)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[5001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
        dp[i] = 1;
    }

    for(int i = 1; i < N; i++){
        for(int j = 0; j < i; j++){
            if(arr[j] < arr[i]){
                dp[i] += dp[j];
                dp[i] %= 998244353;
            }
        }
    }

    for(int i = 0; i < N; i++){
        cout << dp[i] << " ";
    }

    return 0;
}
```