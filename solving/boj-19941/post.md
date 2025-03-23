[문제 바로가기](https://boj.kr/19941)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    string S;
    cin >> N >> K >> S;

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(S[i] != 'P'){
            continue;
        }

        bool isEat = false;
        for(int j = max(i - K, 0); j < min(i + K + 1, N); j++){
            if(i != j && S[j] == 'H'){
                isEat = true;
                S[j] = '_';
                break;
            }
        }
        if(isEat){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
