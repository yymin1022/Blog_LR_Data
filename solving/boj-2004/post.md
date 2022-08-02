[문제 바로가기](https://boj.kr/2004)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, M;
    cin >> N >> M;

    long long two = 0;
    long long five = 0;
    for(long long i = 2; i <= N; i *= 2){
        two += (N / i);
    }
    for(long long i = 5; i <= N; i *= 5){
        five += (N / i);
    }
    for(long long i = 2; i <= M; i *= 2){
        two -= (M / i);
    }
    for(long long i = 5; i <= M; i *= 5){
        five -= (M / i);
    }
    for(long long i = 2; i <= (N - M); i *= 2){
        two -= ((N - M )/ i);
    }
    for(long long i = 5; i <= (N - M); i *= 5){
        five -= ((N - M) / i);
    }
    
    cout << min(five, two) << "\n";

    return 0;
}```