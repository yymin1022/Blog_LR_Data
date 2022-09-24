[문제 바로가기](https://boj.kr/20937)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> dish;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        dish.push_back(input);
    }

    sort(dish.begin(), dish.end(), greater<int>());

    int ans = 1;
    int cnt = 1;
    for(int i = 1; i < N; i++){
        if(dish[i - 1] == dish[i]){
            cnt++;
            ans = max(cnt, ans);
        }else{
            cnt = 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```