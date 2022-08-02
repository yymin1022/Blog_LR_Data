[문제 바로가기](https://boj.kr/2473)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> liquid;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        liquid.push_back(input);
    }

    sort(liquid.begin(), liquid.end());

    long long answer = 3000000001;
    vector<long long> answers(3, 0);
    for(int i = 0; i < N - 2; i++) {
        int fromL = i + 1;
        int fromR = N - 1;
        while (fromL < fromR) {
            long long tempSum = liquid[fromL] + liquid[fromR] + liquid[i];

            if (abs(tempSum) < abs(answer)) {
                answer = tempSum;
                answers[0] = liquid[i];
                answers[1] = liquid[fromL];
                answers[2] = liquid[fromR];
            }

            if (tempSum < 0) {
                fromL++;
            } else if (tempSum > 0) {
                fromR--;
            } else {
                break;
            }
        }
    }

    for(int i = 0; i < 3; i++){
        cout << answers[i] << " ";
    }

    return 0;
}
```