[문제 바로가기](https://boj.kr/2442)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        for(int j = 0; j < N - i; j++){
            cout << " ";
        }
        for(int j = 0; j < i * 2 - 1; j++){
            cout << "*";
        }

        cout << "\n";
    }
    
    return 0;
}```