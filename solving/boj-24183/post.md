[문제 바로가기](https://boj.kr/24183)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    double size[3] = {0.148392, 0.24948, 0.06237};
    double weight = 0;

    for(int i = 0; i < 3; i++){
        int input;
        cin >> input;

        weight += input * size[i];
    }

    cout << weight << "\n";

    return 0;
}```