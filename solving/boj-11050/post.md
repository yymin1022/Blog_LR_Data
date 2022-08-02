[문제 바로가기](https://boj.kr/11050)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    int result = 1;
    for(int i = 0; i < K; i++){
        result *= N;
        N--;
    }

    while(K){
        result /= K;
        K--;
    }

    cout << result << "\n";
    
    return 0;
}```