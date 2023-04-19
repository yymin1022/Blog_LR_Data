[문제 바로가기](https://boj.kr/15565)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input == 1){
            arr.push_back(i);
        }
    }

    if(arr.size() < K){
        cout << -1 << "\n";
        return 0;
    }

    int ans = 2147483647;
    for(int i = 0; i <= arr.size() - K; i++){
        ans = min(arr[i + K - 1] - arr[i] + 1, ans);
    }

    cout << ans << "\n";

    return 0;
}
```