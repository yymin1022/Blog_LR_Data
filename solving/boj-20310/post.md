[문제 바로가기](https://boj.kr/20310)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int cnt0 = 0;
    int cnt1 = 0;
    for(int i = 0; i < S.size(); i++){
        if(S[i] == '0'){
            cnt0++;
        }else{
            cnt1++;
        }
    }

    cnt0 /= 2;
    cnt1 /= 2;

    for(int i = 0; i < S.size(); i++){
        if(cnt1 == 0){
            break;
        }

        if(S[i] == '1'){
            cnt1--;
            S[i] = ' ';
        }
    }

    for(int i = S.size() - 1; i >= 0; i--){
        if(cnt0 == 0){
            break;
        }

        if(S[i] == '0'){
            cnt0--;
            S[i] = ' ';
        }
    }

    for(int i = 0; i < S.size(); i++){
        if(S[i] != ' '){
            cout << S[i];
        }
    }

    return 0;
}

```