[문제 바로가기](https://boj.kr/9610)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> ans(5);
    for(int i = 0; i < N; i++){
        int x, y;
        cin >> x >> y;

        if(!x || !y){
            ans[4]++;
        }else if(x > 0 && y > 0){
            ans[0]++;
        }else if(x < 0 && y > 0){
            ans[1]++;
        }else if(x < 0 && y < 0){
            ans[2]++;
        }else{
            ans[3]++;
        }
    }

    cout << "Q1: " << ans[0] << "\n";
    cout << "Q2: " << ans[1] << "\n";
    cout << "Q3: " << ans[2] << "\n";
    cout << "Q4: " << ans[3] << "\n";
    cout << "AXIS: " << ans[4] << "\n";

    return 0;
}
```