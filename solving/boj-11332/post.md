[문제 바로가기](https://boj.kr/11332)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int C;
    cin >>  C;

    for(int i = 0; i < C; i++){
        long long N, T, L;
        string S;
        cin >> S >> N >> T >> L;

        L *= 100000000;
        long long result;
        if(S == "O(N)"){
            result = N * T;
        }else if(S == "O(N^2)"){
            if(N > 31622) {
                cout << "TLE!" << "\n";
                continue;
            }

            result = N * N * T;
        }else if(S == "O(N^3)"){
            if(N > 1000) {
                cout << "TLE!" << "\n";
                continue;
            }

            result = N * N * N * T;
        }else if(S == "O(2^N)"){
            if(N > 29){
                cout << "TLE!" << "\n";
                continue;
            }

            result = (long long)pow(2, N) * T;
        }else{
            if(N > 12) {
                cout << "TLE!" << "\n";
                continue;
            }

            result = T;
            for(int j = 1; j <= N; j++){
                result *= j;
            }
        }

        if(result > L){
            cout << "TLE!" << "\n";
        }else{
            cout << "May Pass." << "\n";
        }
    }

    return 0;
}```