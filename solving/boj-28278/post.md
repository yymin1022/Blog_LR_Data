[문제 바로가기](https://boj.kr/28278)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    stack<int> stk;
    for(int i = 0; i < N; i++){
        int cmd;
        cin >> cmd;

        if(cmd == 1){
            int input;
            cin >> input;
            stk.push(input);
        }else if(cmd == 2){
            cout << (stk.empty() ? -1 : stk.top()) << "\n";
            if(!stk.empty()){
                stk.pop();
            }
        }else if(cmd == 3){
            cout << stk.size() << "\n";
        }else if(cmd == 4){
            cout << (stk.empty() ? 1 : 0) << "\n";
        }else{
            cout << (stk.empty() ? -1 : stk.top()) << "\n";
        }
    }

    return 0;
}
```