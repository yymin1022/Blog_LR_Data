[문제 바로가기](https://boj.kr/2446)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < i; j++){
            cout << " ";
        }

        for(int j = 0; j < 2 * (N - i) - 1; j++){
            cout << "*";
        }

        cout << "\n";
    }

    for(int i = 2; i <= N; i++){
        for(int j = 0; j < (N - i); j++){
            cout << " ";
        }

        for(int j = 0; j < 2 * i - 1; j++){
            cout << "*";
        }

        cout << "\n";
    }

    return 0;
}```