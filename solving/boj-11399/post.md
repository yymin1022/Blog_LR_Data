[문제 바로가기](https://boj.kr/11399)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> P;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        P.push_back(input);
    }

    sort(P.begin(), P.end());

    int S = 0;
    for(int i = 0; i < N; i++){
        S += P[i] * (N - i);
    }

    cout << S << "\n";

    return 0;
}```