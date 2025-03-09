[문제 바로가기](https://boj.kr/11895)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    int N;
    cin >> N;

    int sum = 0;
    int num = 0;
    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        arr.push_back(input);
        num ^= input;
        sum += input;
    }

    sort(arr.begin(), arr.end());

    cout << (num == 0 ? sum - arr[0] : 0) << "\n";

    return 0;
}
```