[문제 바로가기](https://boj.kr/26574)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        cout << input << " " << input << "\n";
    }

    return 0;
}
```