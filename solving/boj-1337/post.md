[문제 바로가기](https://boj.kr/1337)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int len = 0;
    for(int i = 0; i < N; i++){
        int cnt = 1;
        for(int j = i + 1; j < i + 5; j++){
            if(arr[j] - arr[i] < 5 && arr[j] - arr[i] > 0){
                cnt++;
            }
        }
        len = max(cnt, len);
    }

    cout << (len >= 5 ? 0 : 5 - len) << "\n";

    return 0;
}
```