[문제 바로가기](https://boj.kr/2097)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N < 3){
        cout << N << "\n";
        return 0;
    }

    for(int i = 2; i < N; i++){
        if(N <= i * i){
            cout << (i - 1) * 4 << "\n";
            return 0;
        }else if(N <= i * (i + 1)){
            cout << (i - 1) * 2 + i * 2 << "\n";
            return 0;
        }
    }

    return 0;
}

```