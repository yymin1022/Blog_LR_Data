[문제 바로가기](https://boj.kr/2693)

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
        vector<int> num(10);
        for(int i = 0; i < 10; i++){
            cin >> num[i];
        }

        sort(num.begin(), num.end(), greater<int>());

        cout << num[2] << "\n";
    }

    return 0;
}
```