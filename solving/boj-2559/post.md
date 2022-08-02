[문제 바로가기](https://boj.kr/2559)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> temperature(100001, 0);
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        temperature[i] = temperature[i - 1] + input;
    }

    int answer = -10000000;
    for(int i = 1; i <= N - K + 1; i++){
        int temp = temperature[i + K - 1] - temperature[i - 1];
        answer = max(answer, temp);
    }

    cout << answer << "\n";

    return 0;
}```