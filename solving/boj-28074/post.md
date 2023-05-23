[문제 바로가기](https://boj.kr/28074)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    vector<bool> arr(5, false);
    for(int i = 0; i < S.size(); i++){
        if(S[i] == 'M'){
            arr[0] = true;
        }else if(S[i] == 'O'){
            arr[1] = true;
        }else if(S[i] == 'B'){
            arr[2] = true;
        }else if(S[i] == 'I'){
            arr[3] = true;
        }else if(S[i] == 'S'){
            arr[4] = true;
        }
    }

    for(int i = 0; i < 5; i++){
        if(!arr[i]){
            cout << "NO" << "\n";
            return 0;
        }
    }

    cout << "YES" << "\n";

    return 0;
}
```