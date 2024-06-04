[문제 바로가기](https://boj.kr/12847)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<long long> arr;
    long long tmp = 0;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        arr.push_back(input);

        if(i < M){
            tmp += input;
        }
    }

    long long ans = tmp;
    for(int i = M; i < N; i++){
        tmp += arr[i] - arr[i - M];
        ans = max(tmp, ans);
    }

    cout << ans << "\n";

    return 0;
}
```