[문제 바로가기](https://boj.kr/13900)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long sum = 0;
    long long squareSum = 0;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        squareSum += input * input;
        sum += input;
    }

    cout << (sum * sum - squareSum) / 2 << "\n";

    return 0;
}
```