[문제 바로가기](https://boj.kr/26767)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        if(i % 77 == 0) {
            cout << "Wiwat!" << "\n";
        }else if(i % 7 == 0){
            cout << "Hurra!" << "\n";
        }else if(i % 11 == 0){
            cout << "Super!" << "\n";
        }else{
            cout << i << "\n";
        }
    }

    return 0;
}
```