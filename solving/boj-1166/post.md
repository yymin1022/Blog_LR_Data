[문제 바로가기](https://boj.kr/1166)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, L, W, H;
    cin >> N >> L >> W >> H;

    double left = 0;
    double right = 1000000000;
    for(int i = 0; i < 10000; i++){
        double mid = (left + right) / 2;

        long long tmp = 1;
        tmp *= (long long)(L / mid);
        tmp *= (long long)(W / mid);
        tmp *= (long long)(H / mid);

        if(tmp < N){
            right = mid;
        }else{
            left = mid;
        }
    }

    cout.precision(10);
    cout << fixed;
    cout << left << "\n";

    return 0;
}
```