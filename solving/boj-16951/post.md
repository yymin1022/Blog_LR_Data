[문제 바로가기](https://boj.kr/16951)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 987654321;
    for(int i = 0; i < N; ++i){
        vector<int> tmp(N);
        tmp[i] = arr[i];

        int idx = 0;
        for(int j = i - 1; j >= 0; --j){
            tmp[j] = tmp[j + 1] - K;

            if(tmp[j] <= 0){
                idx = 1;
                break;
            }
        }

        if(idx != 0){
            continue;
        }

        for(int j = i + 1; j < N; j++){
            tmp[j] = tmp[j - 1] + K;
        }

        int cnt = 0;
        for(int j = 0; j < N; j++){
            if(arr[j] != tmp[j]){
                cnt++;
            }
        }

        ans = min(cnt, ans);
    }

    cout << ans << "\n";

    return 0;
}
```