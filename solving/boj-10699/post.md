[문제 바로가기](https://boj.kr/10699)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    char curTime[20];
    time_t now = time(0);
    struct tm  tstruct;
    tstruct = *localtime(&now);
    strftime(curTime, 20, "%F", &tstruct);

    cout << curTime << "\n";

    return 0;
}```