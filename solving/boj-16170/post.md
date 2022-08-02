[문제 바로가기](https://boj.kr/16170)

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
    tstruct = *gmtime(&now);
    strftime(curTime, 20, "%Y\n%m\n%d", &tstruct);

    cout << curTime << "\n";

    return 0;
}```