[문제 바로가기](https://boj.kr/6549)

```c++
#include  <bits/stdc++.h>

using namespace std;

long long histogram[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N){
        histogram[0] = 0;
        histogram[N + 1] = 0;

        for(int i = 1; i <= N; i++){
            cin >> histogram[i];
        }

        stack<long long> stk;
        stk.push(0);

        long long ans = 0;
        for(int i = 1; i <= N + 1; i++){
            while(!stk.empty() && histogram[stk.top()] > histogram[i]){
                long long height = histogram[stk.top()];
                stk.pop();

                long long width = i - stk.top() - 1;
                ans = max(height * width, ans);
            }

            stk.push(i);
        }

        cout << ans << "\n";

        cin >> N;
    }


    return 0;
}
```