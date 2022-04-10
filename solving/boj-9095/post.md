[문제 바로가기](https://boj.kr/9095)

```c++
#include <bits/stdc++.h>

using namespace std;

void dp(int);

int result[11];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    result[1] = 1;
    result[2] = 2;
    result[3] = 4;

    dp(10);

    int T, N;
    cin >> T;

    for(int i = 0; i < T; i++){
        int input;
        cin >> input;
        cout << result[input] << "\n";
    }

    return 0;
}

void dp(int num){
    for(int i = 1; i <= num; i++){
        if(result[i] == 0){
            result[i] = result[i - 1] + result[i - 2] + result[i - 3];
        }
    }
}
```