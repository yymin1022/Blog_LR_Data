[문제 바로가기](https://boj.kr/18698)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        string input;
        cin >> input;

        int cnt = 0;
        for(int i = 0; i < input.size(); i++){
            if(input[i] == 'U'){
                cnt++;
            }else{
                break;
            }
        }

        cout << cnt << "\n";
    }

    return 0;
}
```