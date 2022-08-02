[문제 바로가기](https://boj.kr/2902)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string name;
    cin >> name;

    for(int i = 0; i < name.size(); i++){
        int cur = name[i] - 'A';
        if(cur >= 0 && cur < 27){
            cout << name[i];
        }
    }

    return 0;
}```