[문제 바로가기](https://boj.kr/15820)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int S1, S2;
    cin >> S1 >> S2;

    bool isWhy = false;
    bool isWrong = false;
    for(int i = 0; i < S1; i++){
        int answer, input;
        cin >> answer >> input;

        if(answer != input){
            isWrong = true;
        }
    }
    for(int i = 0; i < S2; i++){
        int answer, input;
        cin >> answer >> input;

        if(answer != input){
            isWhy = true;
        }
    }

    if(isWrong){
        cout << "Wrong Answer" << "\n";
    }else if(isWhy){
        cout << "Why Wrong!!!" << "\n";
    }else{
        cout << "Accepted" << "\n";
    }
    
    return 0;
}```