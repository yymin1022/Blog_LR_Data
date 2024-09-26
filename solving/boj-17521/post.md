[문제 바로가기](https://boj.kr/17521)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, W;
    cin >> N >> W;

    vector<long long> coin;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        coin.push_back(input);
    }

    long long cnt = 0;
    for(int i = 0; i < N - 1; i++){
        if(coin[i] < coin[i + 1]){
            cnt = W / coin[i];
            W %= coin[i];
            W += coin[i + 1] * cnt;
        }
    }

    cout << W << "\n";

    return 0;
}

```