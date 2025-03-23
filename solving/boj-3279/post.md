[문제 바로가기](https://boj.kr/3279)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> rate;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        rate.push_back(input);
    }

    double usd = 100;
    double mks = 0;

    for (int i = 0; i < N; ++i) {
        double tmp_usd = max(usd, mks / rate[i] * 100);
        double tmp_mks = max(mks, usd / 100 * rate[i]);

        usd = tmp_usd;
        mks = tmp_mks;
    }

    cout << fixed << setprecision(2) << usd << "\n";

    return 0;
}
```