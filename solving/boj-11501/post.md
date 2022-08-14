[문제 바로가기](https://boj.kr/11501)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<int> stock;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            stock.push_back(input);
        }

        int maxPrice = 0;
        long long ans = 0;
        for(int i = N - 1; i >= 0; i--){
            maxPrice = max(stock[i], maxPrice);
            ans += maxPrice - stock[i];
        }

        cout << ans << "\n";
    }

    return 0;
}
```