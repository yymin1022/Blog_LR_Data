[문제 바로가기](https://boj.kr/9085)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        int sum = 0;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            sum += input;
        }
        cout << sum << "\n";
    }
}
```