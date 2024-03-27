[문제 바로가기](https://boj.kr/23827)

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
    vector<long long> sum;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
        sum.push_back(input);

        if(i > 0){
            sum[i] += sum[i - 1];
        }
    }

    long long ans = 0;
    for(int i = 0; i < N; i++){
        ans += ((sum[N - 1] - sum[i]) * arr[i]) % 1000000007;
    }

    cout << ans % 1000000007 << "\n";

    return 0;
}
```