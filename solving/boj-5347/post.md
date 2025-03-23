[문제 바로가기](https://boj.kr/5347)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N--){
        long long A, B;
        cin >> A >> B;

        long long tmpA = max(A, B);
        long long tmpB = min(A, B);

        while(tmpB > 0){
            long long tmp = tmpA % tmpB;
            tmpA = tmpB;
            tmpB = tmp;
        }

        cout << (A * B) / tmpA << "\n";
	}

    return 0;
}
```
