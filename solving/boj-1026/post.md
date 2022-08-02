[문제 바로가기](https://boj.kr/1026)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> A;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        A.push_back(input);
    }

    vector<int> B;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        B.push_back(input);
    }

    sort(A.begin(), A.end());
    sort(B.rbegin(), B.rend());

    int sum = 0;
    for(int i = 0; i < N; i++){
        sum += A[i] * B[i];
    }

    cout << sum << "\n";

    return 0;
}```