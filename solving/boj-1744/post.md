[문제 바로가기](https://boj.kr/1744)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> plus;
    vector<int> minus;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input > 0){
            plus.push_back(input);
        }else{
            minus.push_back(input);
        }
    }

    sort(plus.begin(), plus.end());
    sort(minus.rbegin(), minus.rend());

    int ans = 0;
    while(!plus.empty()){
        if(plus.size() > 1){
            if(plus[plus.size() - 1] > 1 && plus[plus.size() - 2] > 1){
                ans += plus[plus.size() - 1] * plus[plus.size() - 2];
            }else{
                ans += plus[plus.size() - 1] + plus[plus.size() - 2];
            }
            
            plus.pop_back();
            plus.pop_back();
        }else{
            ans += plus[plus.size() - 1];
            plus.pop_back();
        }
    }

    while(!minus.empty()){
        if(minus.size() > 1){
            ans += minus[minus.size() - 1] * minus[minus.size() - 2];

            minus.pop_back();
            minus.pop_back();
        }else{
            ans += minus[minus.size() - 1];
            minus.pop_back();
        }
    }

    cout << ans << "\n";

    return 0;
}
```