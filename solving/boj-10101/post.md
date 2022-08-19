[문제 바로가기](https://boj.kr/10101)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    cin >> A >> B >> C;

    string result = "Scalene";
    if(A + B + C != 180){
        result = "Error";
    }else if(A == 60 && B == 60){
        result = "Equilateral";
    }else if(A == B || B == C || A == C){
        result = "Isosceles";
    }

    cout << result << "\n";

    return 0;
}
```