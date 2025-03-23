[문제 바로가기](https://boj.kr/23278)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, L, H;
    cin >> N >> L >> H;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    double sum = 0;
    for(int i = L; i < N - H; i++){
        sum += arr[i];
    }

    cout.precision(10);
    cout << fixed << sum / (N - L - H) << "\n";

    return 0;
}
```