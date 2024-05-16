[문제 바로가기](https://boj.kr/21966)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    string S;
    cin >> S;

    if(N <= 25){
        cout << S << "\n";
        return 0;
    }

    bool flag = true;
    for(int i = 12; i < N - 12; i++){
        if(S[i] == '.'){
            flag = false;
            break;
        }
    }

    if(flag){
        cout << S.substr(0, 11) << "..." << S.substr(N - 11, 11) << "\n";
    }else{
        cout << S.substr(0, 9) << "......" << S.substr(N - 10, 10) << "\n";
    }

    return 0;
}
```