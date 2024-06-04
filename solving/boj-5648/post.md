[문제 바로가기](https://boj.kr/5648)

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
        string input;
        cin >> input;
        reverse(input.begin(), input.end());
        arr.push_back(stol(input));
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N; i++){
        cout << arr[i] << "\n";
    }

    return 0;
}
```