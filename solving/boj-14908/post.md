[문제 바로가기](https://boj.kr/14908)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<double, int>> arr;
    for(int i = 1; i <= N; i++){
        double T, S;
        cin >> T >> S;
        arr.push_back(make_pair(T / S, i));
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N; i++){
        cout << arr[i].second << " ";
    }

    return 0;
}
```