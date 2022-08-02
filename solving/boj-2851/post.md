[문제 바로가기](https://boj.kr/2851)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int maxV = 0;
    vector<int> mushroom(11);
    for(int i = 1; i <= 10; i++){
        cin >> mushroom[i];
        mushroom[i] += mushroom[i - 1];

        if(abs(100 - mushroom[i]) <= abs(100 - maxV)){
            maxV = mushroom[i];
        }
    }

    cout << maxV << "\n";

    return 0;
}```