[문제 바로가기](https://boj.kr/11382)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long sum = 0;
    for(int i = 0; i < 3; i++){
        long long num;
        cin >> num;
        sum += num;
    }

    cout << sum << "\n";

    return 0;
}```