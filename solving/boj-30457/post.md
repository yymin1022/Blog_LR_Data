[문제 바로가기](https://boj.kr/30457)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<int, int> height;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        height[input]++;
    }

    int ans = 0;
    for(auto iter = height.begin(); iter != height.end(); iter++){
        if(iter->second > 1){
            ans += 2;
        }else{
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
