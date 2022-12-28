[문제 바로가기](https://boj.kr/2566)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    vector<int> ans(3, 0);
    for(int i = 0; i < 9; i++){
        for(int j = 0; j < 9; j++){
            int input;
            cin >> input;

            if(input >= ans[0]){
                ans[0] = input;
                ans[1] = i + 1;
                ans[2] = j + 1;
            }
        }
    }

    cout << ans[0] << "\n";
    cout << ans[1] << " " << ans[2] << "\n";
    
    return 0;
}
```