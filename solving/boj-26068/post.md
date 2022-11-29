[문제 바로가기](https://boj.kr/26068)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        string temp = input.substr(2, input.size() - 2);
        if(stoi(temp) <= 90){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```