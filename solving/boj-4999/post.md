[문제 바로가기](https://boj.kr/4999)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string able;
    string doctor;
    cin >> able >> doctor;

    if(able.size() < doctor.size()){
        cout << "no" << "\n";
    }else{
        cout << "go" << "\n";
    }

    return 0;
}```