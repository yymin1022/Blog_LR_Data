[문제 바로가기](https://boj.kr/5576)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> W;
    for(int i = 0; i < 10; i++){
        int input;
        cin >> input;
        W.push_back(input);
    }
    vector<int> K;
    for(int i = 0; i < 10; i++){
        int input;
        cin >> input;
        K.push_back(input);
    }

    sort(W.begin(), W.end(), greater<int>());
    sort(K.begin(), K.end(), greater<int>());

    int scoreK = 0;
    int scoreW = 0;
    for(int i = 0; i < 3; i++){
        scoreK += K[i];
        scoreW += W[i];
    }

    cout << scoreW << " " << scoreK << "\n";

    return 0;
}
```