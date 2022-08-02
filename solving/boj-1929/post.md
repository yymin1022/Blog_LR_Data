[문제 바로가기](https://boj.kr/1929)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long M, N;
    cin >> M >> N;

    for(long long i = M; i <= N; i++){
        bool isOK = true;
        if(i < 2){
            isOK = false;
        }
        for(long long j = 2; j <= sqrt(i); j++){
            if(i % j == 0){
                isOK = false;
                break;
            }
        }
        if(isOK){
            cout << i << "\n";
        }
    }
    
    return 0;
}```