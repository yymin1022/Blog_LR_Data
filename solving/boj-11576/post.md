[문제 바로가기](https://boj.kr/11576)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, M;
    cin >> A >> B >> M;

    vector<int> numA;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        numA.push_back(input);
    }

    int dec = 0;
    for(int i = 0; i < M; i++){
        dec += numA[M - i - 1] * pow(A, i);
    }

    vector<int> numB;
    while(dec){
        numB.push_back(dec % B);
        dec /= B;
    }

    for(int i = numB.size() - 1; i >= 0; i--){
        cout << numB[i] << " ";
    }

    return 0;
}
```