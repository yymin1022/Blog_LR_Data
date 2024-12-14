[문제 바로가기](https://boj.kr/3054)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    for(int i = 0; i < S.size(); i++){
        if((i + 1) % 3 == 0){
            cout << "..*.";
        }else{
            cout << "..#.";
        }

        if(i == S.size() - 1){
            cout << "." << "\n";
        }
    }

    for(int i = 0; i < S.size(); i++){
        if((i + 1) % 3 == 0){
            cout << ".*.*";
        }else{
            cout << ".#.#";
        }

        if(i == S.size() - 1){
            cout << "." << "\n";
        }
    }

    for(int i = 0; i < S.size(); i++){
        if(i > 0 && i % 3 == 0 || (i + 1) % 3 == 0){
            cout << "*";
        }else{
            cout << "#";
        }

        cout << "." << S[i] << ".";

        if(i == S.size() - 1){
            if((i + 1) % 3 == 0){
                cout << "*" << "\n";
            }else{
                cout << "#" << "\n";
            }
        }
    }

    for(int i = 0; i < S.size(); i++){
        if((i + 1) % 3 == 0){
            cout << ".*.*";
        }else{
            cout << ".#.#";
        }

        if(i == S.size() - 1){
            cout << "." << "\n";
        }
    }

    for(int i = 0; i < S.size(); i++){
        if((i + 1) % 3 == 0){
            cout << "..*.";
        }else{
            cout << "..#.";
        }

        if(i == S.size() - 1){
            cout << "." << "\n";
        }
    }

    return 0;
}
```