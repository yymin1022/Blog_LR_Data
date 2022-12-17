[문제 바로가기](https://boj.kr/26257)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, Q;
    cin >> N >> M >> Q;

    vector<int> pointer(M + 1, 0);
    for(int i = 1; i <= M; i++){
        cin >> pointer[i];
    }

    for(int i = 0; i < Q; i++){
        string cmd;
        cin >> cmd;

        int a, b;
        if(cmd == "assign"){
            cin >> a >> b;
            pointer[a] = pointer[b];
        }else if(cmd == "swap"){
            cin >> a >> b;
            int tmp = pointer[a];
            pointer[a] = pointer[b];
            pointer[b] = tmp;
        }else{
            cin >> a;
            pointer[a] = 0;
        }
    }

    int cnt = 0;
    vector<bool> result(M + 1, false);
    for(int i = 1; i <= M; i++){
        if(pointer[i] && !result[pointer[i]]){
            cnt++;
            result[pointer[i]] = true;
        }
    }

    cout << cnt << "\n";
    for(int i = 1; i <= M; i++){
        if(result[i]){
            cout << i << "\n";
        }
    }

    return 0;
}
```