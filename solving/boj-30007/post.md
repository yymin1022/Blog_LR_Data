[문제 바로가기](https://boj.kr/30007)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N--){
        int A, B, X;
        cin >> A >> B >> X;
        cout << A * (X - 1) + B << "\n";
    }

    return 0;
}
```
