[문제 바로가기](https://boj.kr/2745)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string N;
    int B;
    cin >> N >> B;

    int sum(0);
    for(int i = 0; i < N.length(); i++){
        int tmp = N[N.length() - (i + 1)];

        if('0' <= tmp && tmp <= '9'){
            tmp = tmp - '0';
        }else{
            tmp = tmp + 10 - 'A';
        }

        sum += (tmp * (int)pow(B, i));
    }

    cout << sum << '\n';

    return 0;
}
```