[문제 바로가기](https://boj.kr/20115)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<double> arr;
    for(int i = 0; i < N; i++){
        double input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    double ans = arr[N - 1];
    for(int i = 0; i < N - 1; i++){
        ans += arr[i] / 2;
    }

    cout << ans << "\n";

    return 0;
}

```
