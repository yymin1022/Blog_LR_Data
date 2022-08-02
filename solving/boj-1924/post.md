[문제 바로가기](https://boj.kr/1924)

```c++
#include <bits/stdc++.h>

using namespace std;

int days[13] = { 0,31,28,31,30,31,30,31,31,30,31,30,31 };
string day[7] { "SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT" };

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int month, date;
    cin >> month >> date;

    for (int i = 1; i < month; ++i) {
	date += days[i];
    }
    
    cout << day[date % 7] << "\n";

    return 0;
}
```