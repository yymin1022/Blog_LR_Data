[문제 바로가기](https://boj.kr/14655)

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
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        ans += abs(input);
    }

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        ans += abs(input);
    }

    cout << ans << "\n";

    return 0;
}
```