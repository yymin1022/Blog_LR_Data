[문제 바로가기](https://boj.kr/3022)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    int cnt = 0;
    map<string, int> data;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        if(cnt - data[input] < data[input]){
            ans++;
        }

        cnt++;
        data[input]++;
    }

    cout << ans << "\n";

    return 0;
}
```