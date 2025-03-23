[문제 바로가기](https://boj.kr/2812)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    string S;
    cin >> N >> K >> S;

    int cnt = 0;
    stack<char> stk;
    for(int i = 0; i < S.size(); i++){
        while(!stk.empty() && stk.top() < S[i] && cnt < K){
            stk.pop();
            cnt++;
        }
        stk.push(S[i]);
    }

    string ans;
    while(!stk.empty()){
        ans.push_back(stk.top());
        stk.pop();
    }

    reverse(ans.begin(), ans.end());

    for(int i = 0; i < N - K; i++){
        cout << ans[i];
    }

    return 0;
}
```