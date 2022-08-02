[문제 바로가기](https://boj.kr/2525)

```c++
#include <iostream>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int hour;
    int min;
    int time;

    cin >> hour >> min >> time;

    min += time;

    while(min >= 60){
        hour += 1;
        min -= 60;
    }

    if(hour >= 24){
        hour -= 24;
    }

    cout << hour << " " << min;

    return 0;
}```