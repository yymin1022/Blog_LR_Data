[문제 바로가기](https://boj.kr/4766)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    double temp;
    cin >> temp;

    cout << fixed;
    cout.precision(2);
    while(true){
        double input;
        cin >> input;
        if(int(input) == 999){
            break;
        }

        cout << input - temp << "\n";
        temp = input;
    }

    return 0;
}
```