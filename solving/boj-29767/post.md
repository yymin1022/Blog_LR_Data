[문제 바로가기](https://boj.kr/29767)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);

        if(i > 0){
            arr[i] += arr[i - 1];
        }
    }

    sort(arr.begin(), arr.end(), greater<long long>());

    long long ans = 0;
    for(int i = 0; i < K; i++){
        ans += arr[i];
    }

    cout << ans << "\n";

    return 0;
}
```
