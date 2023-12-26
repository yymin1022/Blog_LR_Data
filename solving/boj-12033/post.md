[문제 바로가기](https://boj.kr/12033)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int N;
        cin >> N;

        vector<int> price;
        for(int i = 0; i < N * 2; i++){
            int input;
            cin >> input;
            price.push_back(input);
        }

        vector<int> ans;
        for(int i = N * 2 - 1; i >= 0; i--){
            if(price[i] != 0){
                for(int j = i - 1; j >= 0; j--){
                    if(price[j] % 3 == 0 && price[j] / 3 == price[i] / 4){
                        ans.push_back(price[j]);
                        price[j] = 0;
                        break;
                    }
                }
            }
        }

        cout << "Case #" << t << ": ";
        for(int i = ans.size() - 1; i >= 0; i--){
            cout << ans[i] << " ";
        }
        cout << "\n";
    }

    return 0;
}
```
