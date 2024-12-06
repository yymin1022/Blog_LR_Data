[문제 바로가기](https://boj.kr/14720)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> store;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        store.push_back(input);
    }

    int ans = 0;
    int curMilk = 0;
    int milkType[3] = {0, 1, 2};
    for(int i = 0; i < N; i++){
        if(store[i] == curMilk){
            ans++;
            curMilk = milkType[(curMilk + 1) % 3];
        }
    }

    cout << ans << "\n";

    return 0;
}
```