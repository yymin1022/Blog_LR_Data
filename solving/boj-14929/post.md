[문제 바로가기](https://boj.kr/14929)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        arr.push_back(input);

        if(i > 0){
            arr[i] += arr[i - 1];
        }
    }

    long long ans = 0;
    for(int i = 0; i < N; i++){
        ans += (arr[N - 1] - arr[i]) * (arr[i] - (i > 0 ? arr[i - 1] : 0));
    }

    cout << ans << "\n";

    return 0;
}
```