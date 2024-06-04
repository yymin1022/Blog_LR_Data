[문제 바로가기](https://boj.kr/9711)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int P, Q;
        cin >> P >> Q;

        vector<long long> fibo(P + 1, 0);
        fibo[1] = 1;
        fibo[2] = 1;
        for(int i = 3; i <= P; i++){
            fibo[i] = (fibo[i - 1] + fibo[i - 2]) % Q;
        }

        cout << "Case #" << t << ": ";
        cout << fibo[P] % Q << "\n";
    }

    return 0;
}
```