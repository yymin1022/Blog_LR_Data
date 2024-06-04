[문제 바로가기](https://boj.kr/17262)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int maxVal = 1;
    int minVal = 100000;
    for(int i = 0; i < N; i++){
        int S, E;
        cin >> S >> E;
        maxVal = max(S, maxVal);
        minVal = min(E, minVal);
    }

    cout << max(maxVal - minVal, 0) << "\n";

    return 0;
}

```