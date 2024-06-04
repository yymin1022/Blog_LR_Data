[문제 바로가기](https://boj.kr/20116)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    double tmp = arr[N - 1];
    int cnt = 1;
    for(int i = N - 2; i >= 0; i--){
        if(arr[i] > arr[i + 1] + L || arr[i] < arr[i + 1] - L
            || tmp >= arr[i] + L || tmp <= arr[i] - L){
            cout << "unstable" << "\n";
            return 0;
        }
        tmp = (tmp * cnt + arr[i]) / (cnt + 1);
        cnt++;
    }

    cout << "stable" << "\n";

    return 0;
}
```
