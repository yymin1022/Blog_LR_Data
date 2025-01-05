[문제 바로가기](https://boj.kr/18311)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    for(long long i = 0; i < N; i++){
        K -= arr[i];

        if(K < 0){
            cout << i + 1 << "\n";
            return 0;
        }
    }

    for(long long i = N - 1; i >= 0; i--){
        K -= arr[i];

        if(K < 0){
            cout << i + 1 << "\n";
            return 0;
        }
    }

    return 0;
}
```