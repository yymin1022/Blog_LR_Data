[문제 바로가기](https://boj.kr/20551)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < M; i++){
        int D;
        cin >> D;

        int idx = lower_bound(arr.begin(), arr.end(), D) - arr.begin();
        cout << (arr[idx] != D || idx >= N ? -1 : idx) << "\n";
    }

    return 0;
}

```
