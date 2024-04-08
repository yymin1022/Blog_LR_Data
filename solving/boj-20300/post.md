[문제 바로가기](https://boj.kr/20300)

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
    }

    sort(arr.begin(), arr.end());

    long long ans = 0;
    if(N % 2){
        ans = arr[N - 1];
        for(int i = 0; i < N / 2; i++){
            long long M = arr[i] + arr[N - i - 2];
            ans = max(M, ans);
        }
    }else{
        for(int i = 0; i < N / 2; i++){
            long long M = arr[i] + arr[N - i - 1];
            ans = max(M, ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```