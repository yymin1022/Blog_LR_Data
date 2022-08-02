[문제 바로가기](https://boj.kr/2435)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> tempSum;
    tempSum.push_back(0);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        tempSum.push_back(input + tempSum[i]);
    }

    int maxTemp = -100;
    for(int i = K; i <= N; i++){
        maxTemp = max(maxTemp, tempSum[i] - tempSum[i - K]);
    }

    cout << maxTemp << "\n";

    return 0;
}```