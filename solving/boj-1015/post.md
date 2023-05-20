[문제 바로가기](https://boj.kr/1015)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> A;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        A.push_back(make_pair(input, i));
    }

    sort(A.begin(), A.end());

    vector<int> B(N);
    for(int i = 0; i < N; i++){
        B[A[i].second] = i;
    }

    for(int i = 0; i < N; i++){
        cout << B[i] << " ";
    }

    return 0;
}
```