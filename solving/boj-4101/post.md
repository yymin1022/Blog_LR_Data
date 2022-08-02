[문제 바로가기](https://boj.kr/4101)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    while(A && B){
        if(A > B){
            cout << "Yes" << "\n";
        }else{
            cout << "No" << "\n";
        }

        cin >> A >> B;
    }

    return 0;
}```