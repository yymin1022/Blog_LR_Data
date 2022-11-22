[문제 바로가기](https://boj.kr/24883)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    char input;
    cin >> input;

    if(input == 'N' || input == 'n'){
        cout << "Naver D2" << "\n";
    }else{
        cout << "Naver Whale" << "\n";
    };

    return 0;
}
```