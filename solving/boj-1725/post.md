[문제 바로가기](https://boj.kr/1725)

```c++
#include  <bits/stdc++.h>

using namespace std;

int histogram[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        histogram[i] = input;
    }

    stack<int> stk;
    stk.push(0);

    int ans = 0;
    for(int i = 1; i <= N + 1; i++){
        while(!stk.empty() && histogram[stk.top()] > histogram[i]){
            int height = histogram[stk.top()];
            stk.pop();

            int width = i - stk.top() - 1;
            ans = max(height * width, ans);
        }

        stk.push(i);
    }

    cout << ans << "\n";
    
    return 0;
}
```