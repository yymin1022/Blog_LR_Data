[문제 바로가기](https://boj.kr/2869)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int A, B, V;
    cin >> A >> B >> V;

    int day = (V - A) / (A - B) + 1;

    if((V - A) % (A - B) != 0){
        day++;
    }

    cout << day;
}
```