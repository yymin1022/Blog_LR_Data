[문제 바로가기](https://boj.kr/2864)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string A, B;
    cin >> A >> B;

    for(int i = 0; i < A.size(); i++){
        if(A[i] == '6'){
            A[i] = '5';
        }
    }
    for(int i = 0; i < B.size(); i++){
        if(B[i] == '6'){
            B[i] = '5';
        }
    }

    cout << stoi(A) + stoi(B) << " ";

    for(int i = 0; i < A.size(); i++){
        if(A[i] == '5'){
            A[i] = '6';
        }
    }
    for(int i = 0; i < B.size(); i++){
        if(B[i] == '5'){
            B[i] = '6';
        }
    }

    cout << stoi(A) + stoi(B) << "\n";

    return 0;
}
```