[문제 바로가기](https://boj.kr/9461)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<long long> arr;
    arr.push_back(1);
    arr.push_back(1);
    arr.push_back(1);
    arr.push_back(2);
    arr.push_back(2);
    for(int i = 5; i <= 100; i++){
        arr.push_back(arr[i - 1] + arr[i - 5]);
    }

    int T;
    cin >> T;
    for(int i = 0; i < T; i++){
        int N;
        cin >> N;

        cout << arr[N - 1] << "\n";
    }

    return 0;
}
```