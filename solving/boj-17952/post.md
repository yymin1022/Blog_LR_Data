[문제 바로가기](https://boj.kr/17952)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    stack<pair<int, int>> stk;
    for(int i = 0; i < N; i++){
        int cmd;
        cin >> cmd;

        if(cmd == 1){
            int A, T;
            cin >> A >> T;
            stk.push(make_pair(A, T));
        }

        if(!stk.empty()){
            stk.top().second--;

            if(stk.top().second == 0){
                ans += stk.top().first;
                stk.pop();
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```