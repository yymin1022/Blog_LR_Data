[문제 바로가기](https://boj.kr/16200)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> X;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        X.push_back(input);
    }

    sort(X.begin(), X.end());

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(X[i] > 0){
            for(int j = 1; j < X[i] && i + j < N; j++){
                X[i + j] = 0;
            }
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
