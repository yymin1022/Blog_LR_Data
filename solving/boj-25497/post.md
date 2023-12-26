[문제 바로가기](https://boj.kr/25497)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    string cmd;
    cin >> cmd;

    int ans = 0;
    stack<char> skillL;
    stack<char> skillS;
    for(int i = 0; i < N; i++){
        if(cmd[i] >= '0' && cmd[i] <= '9'){
            ans++;
        }else if(cmd[i] == 'L'){
            skillL.push(cmd[i]);
        }else if(cmd[i] == 'S'){
            skillS.push(cmd[i]);
        }else if(cmd[i] == 'R'){
            if(skillL.empty()){
                cout << ans << "\n";
                return 0;
            }
            ans++;
            skillL.pop();
        }else if(cmd[i] == 'K'){
            if(skillS.empty()){
                cout << ans << "\n";
                return 0;
            }
            ans++;
            skillS.pop();
        }
    }

    cout << ans << "\n";

    return 0;
}

```