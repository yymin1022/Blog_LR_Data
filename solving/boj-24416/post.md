[문제 바로가기](https://boj.kr/24416)

```c++
#include <bits/stdc++.h>

using namespace std;

int fibonacciDP(int);
int fibonacciRec(int);

int cntDP;
int cntRec;
int dp[41];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 1;

    fibonacciDP(N);
    fibonacciRec(N);

    cout << cntRec << " ";
    cout << cntDP << " ";

    return 0;
}

int fibonacciDP(int N){
    if(!dp[N]){
        cntDP++;
        dp[N] = fibonacciDP(N - 1) + fibonacciDP(N - 2);
    }

    return dp[N];
}

int fibonacciRec(int N){
    if(N <= 2){
        cntRec++;
        return 1;
    }

    return fibonacciRec(N - 1) + fibonacciRec(N - 2);
}```