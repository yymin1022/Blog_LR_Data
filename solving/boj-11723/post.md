[문제 바로가기](https://boj.kr/11723)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    set<int> S;
    
    int M;
    cin >> M;

    for(int i = 0; i < M; i++){
        int x;
        string cmd;
        cin >> cmd;

        if(cmd == "add"){
            cin >> x;
            S.insert(x);
        }else if(cmd == "remove"){
            cin >> x;
            S.erase(x);
        }else if(cmd == "check"){
            cin >> x;
            if(S.find(x) != S.end()){
                cout << 1 << "\n";
            }else{
                cout << 0 << "\n";
            }
        }else if(cmd == "toggle"){
            cin >> x;
            if(S.find(x) != S.end()){
                S.erase(x);
            }else{
                S.insert(x);
            }
        }else if(cmd == "all"){
            for(int i = 0; i <= 20; i++){
                S.insert(i);
            }
        }else if(cmd == "empty"){
            S.clear();
        }
    }

    return 0;
}
```