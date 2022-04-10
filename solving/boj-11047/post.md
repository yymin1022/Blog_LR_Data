[문제 바로가기](https://boj.kr/11047)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> coin;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        coin.push_back(input);
    }

    reverse(coin.begin(), coin.end());

    int cnt = 0;
    for(int i = 0; i < coin.size(); i++){
        if(K == 0){
            break;
        }

        cnt += K / coin[i];
        K %= coin[i];
    }

    cout << cnt << "\n";

    return 0;
}
```